# Setting Up Nginx and TYPO3 CMS on Debian 12

This guide will help you set up nginx and TYPO3 CMS on your headless Debian 12 machine.

## Prerequisites
- SSH access to your Debian 12 machine
- Root or sudo privileges

## Step 1: Install Nginx Web Server

SSH into your remote machine:
```bash
ssh username@your_remote_ip
```

Update your system:
```bash
sudo apt update
sudo apt upgrade -y
```

Install Nginx:
```bash
sudo apt install nginx -y
```

Start and enable Nginx:
```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

Check if Nginx is running:
```bash
sudo systemctl status nginx
```

Configure firewall to allow HTTP and HTTPS traffic:
```bash
sudo apt install ufw -y
sudo ufw allow 'Nginx Full'
sudo ufw enable
```

## Step 2: Install MariaDB (MySQL)

Install MariaDB:
```bash
sudo apt install mariadb-server mariadb-client -y
```

Start and enable MariaDB:
```bash
sudo systemctl start mariadb
sudo systemctl enable mariadb
```

Secure your MariaDB installation:
```bash
sudo mysql_secure_installation
```
- Press Enter for the current password (there is none by default)
- Type 'Y' to set a root password, and enter a strong password
- Answer 'Y' to all remaining questions

Create a database and user for TYPO3:
```bash
sudo mysql -u root -p
```

Once in the MySQL prompt, run:
```sql
CREATE DATABASE typo3db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'typo3user'@'localhost' IDENTIFIED BY 'your_strong_password';
GRANT ALL PRIVILEGES ON typo3db.* TO 'typo3user'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

## Step 3: Install PHP and Required Extensions

TYPO3 requires PHP 8.1 or higher. Let's install PHP 8.2:

```bash
sudo apt install php8.2-fpm php8.2-cli php8.2-common php8.2-mysql php8.2-zip php8.2-gd php8.2-mbstring php8.2-curl php8.2-xml php8.2-bcmath php8.2-intl php8.2-soap php8.2-imap php8.2-opcache php8.2-apcu -y
```

Check PHP version:
```bash
php -v
```

Configure PHP-FPM:
```bash
sudo nano /etc/php/8.2/fpm/php.ini
```

Make the following adjustments:
```
upload_max_filesize = 50M
post_max_size = 50M
memory_limit = 256M
max_execution_time = 240
date.timezone = Your/Timezone
```

Restart PHP-FPM:
```bash
sudo systemctl restart php8.2-fpm
```

## Step 4: Install Composer

Install Composer (PHP dependency manager):
```bash
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
```

Verify the installation:
```bash
composer --version
```

## Step 5: Download and Set Up TYPO3

Create a web directory for your TYPO3 installation:
```bash
sudo mkdir -p /var/www/typo3
sudo chown -R www-data:www-data /var/www/typo3
sudo chmod -R 775 /var/www/typo3
```

Add your user to the www-data group to easily manage files:
```bash
sudo usermod -a -G www-data $USER
```

Log out and log back in for the group changes to take effect:
```bash
exit
# SSH back in
ssh username@your_remote_ip
```

Navigate to the web directory:
```bash
cd /var/www/typo3
```

Download TYPO3 using Composer:
```bash
composer create-project typo3/cms-base-distribution .
```

Set proper permissions for TYPO3:
```bash
sudo chown -R www-data:www-data /var/www/typo3
sudo find /var/www/typo3 -type d -exec chmod 755 {} \;
sudo find /var/www/typo3 -type f -exec chmod 644 {} \;
sudo mkdir -p /var/www/typo3/var/{assets,indexes,lock,log,transient}
sudo chmod -R 777 /var/www/typo3/var
```

## Step 6: Configure Nginx for TYPO3

Create a server block for TYPO3:
```bash
sudo nano /etc/nginx/sites-available/typo3
```

Add the following configuration:
```nginx
server {
    listen 80;
    server_name localhost; # Or your IP address or domain
    root /var/www/typo3/public;
    index index.php index.html;

    location / {
        try_files $uri $uri/ /index.php$is_args$args;
    }

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.2-fpm.sock;
        fastcgi_index index.php;
        include fastcgi_params;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        fastcgi_param PATH_INFO $fastcgi_path_info;
        fastcgi_param TYPO3_CONTEXT Development;
    }

    # Static files
    location ~* \.(jpg|jpeg|png|gif|ico|css|js)$ {
        expires max;
        log_not_found off;
    }

    # Deny access to sensitive files
    location ~ /\.ht {
        deny all;
    }
    
    location ~ \.git {
        deny all;
    }

    client_max_body_size 50m;
}
```

Enable the site:
```bash
sudo ln -s /etc/nginx/sites-available/typo3 /etc/nginx/sites-enabled/
sudo rm /etc/nginx/sites-enabled/default # Remove default site
sudo nginx -t # Test the configuration
sudo systemctl reload nginx
```

## Step 7: Complete TYPO3 Installation

Access the TYPO3 installation wizard by navigating to your server's IP address in a web browser:
```
http://your_server_ip
```

Follow the TYPO3 installation wizard:
1. Select language
2. Check system environment (fix any issues)
3. Database connection:
   - Username: typo3user
   - Password: your_strong_password
   - Host: localhost
   - Database: typo3db
4. Create an admin user
5. Select a site setup

## Step 8: Development Access

For remote development, you can access your web server through SSH tunneling:

```bash
ssh -L 8080:localhost:80 username@your_remote_ip
```

Then access your TYPO3 installation at:
```
http://localhost:8080
```

Alternatively, you can allow external access by modifying your firewall settings:
```bash
sudo ufw allow 80/tcp
```

## Step 9: Install Git for Version Control

```bash
sudo apt install git -y
```

Configure Git:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Additional Tips

1. **Performance Monitoring:**
   ```bash
   sudo apt install htop -y
   ```

2. **Regular Backups:**
   Create a backup script for your TYPO3 site:
   ```bash
   sudo nano /opt/backup-typo3.sh
   ```
   
   Add this content:
   ```bash
   #!/bin/bash
   BACKUP_DIR="/opt/backups/typo3"
   MYSQL_USER="typo3user"
   MYSQL_PASS="your_strong_password"
   MYSQL_DB="typo3db"
   DATE=$(date +%Y-%m-%d_%H-%M-%S)
   
   # Create backup directory if it doesn't exist
   mkdir -p $BACKUP_DIR
   
   # Backup the database
   mysqldump -u $MYSQL_USER -p$MYSQL_PASS $MYSQL_DB > $BACKUP_DIR/typo3db_$DATE.sql
   
   # Backup the files
   tar -czf $BACKUP_DIR/typo3_files_$DATE.tar.gz -C /var/www/typo3 .
   
   # Remove backups older than 7 days
   find $BACKUP_DIR -type f -name "*.sql" -mtime +7 -delete
   find $BACKUP_DIR -type f -name "*.tar.gz" -mtime +7 -delete
   ```
   
   Make it executable:
   ```bash
   sudo chmod +x /opt/backup-typo3.sh
   ```
   
   Add it to crontab for automatic daily backups:
   ```bash
   sudo crontab -e
   ```
   
   Add this line:
   ```
   0 4 * * * /opt/backup-typo3.sh
   ```
