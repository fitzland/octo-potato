---
tags:
	- howto
---

# Setting Up a Minecraft Server on Debian 12

## Prerequisites
- Debian 12 system
- Root or sudo access
- Open port (default: 25565) on your router/firewall

## Step 1: Update Your System
```bash
sudo apt update
sudo apt upgrade -y
```

## Step 2: Install Java
Minecraft server requires Java. For the latest versions, OpenJDK 17 is recommended.

```bash
sudo apt install openjdk-17-jre-headless -y
```

Verify Java installation:
```bash
java -version
```

## Step 3: Create a Minecraft User and Directory
For security, create a dedicated user:

```bash
sudo useradd -m -r -d /opt/minecraft minecraft
sudo mkdir -p /opt/minecraft/server
sudo chown -R minecraft:minecraft /opt/minecraft
```

## Step 4: Download the Minecraft Server
Switch to the minecraft user:

```bash
sudo su - minecraft
cd /opt/minecraft/server
```

Download the latest server JAR (check the [Minecraft website](https://www.minecraft.net/en-us/download/server) for the latest version):

```bash
wget https://piston-data.mojang.com/v1/objects/e6ec2f64e6080b9b5d9b471b291c33cc7f509733/server.jar -O minecraft_server.jar
```

## Step 5: Accept the EULA
Run the server once:

```bash
java -Xmx4G -Xms1G -jar minecraft_server.jar nogui
```

This will fail, but generate the EULA file. Edit and accept the EULA:

```bash
echo "eula=true" > eula.txt
```

## Step 6: Configure Server Properties
Edit the server.properties file:

```bash
nano server.properties
```

Some recommended settings:
```
gamemode=survival
difficulty=normal
max-players=10
view-distance=10
server-port=25565
enable-command-block=true
motd=My Debian 12 Minecraft Server
```

## Step 7: Create a Systemd Service
Exit to your regular user:

```bash
exit
```

Create a systemd service file:

```bash
sudo nano /etc/systemd/system/minecraft.service
```

Add the following:

```
[Unit]
Description=Minecraft Server
After=network.target

[Service]
User=minecraft
Nice=5
KillSignal=SIGINT
TimeoutStopSec=120
SuccessExitStatus=0 1
ProtectHome=true
ProtectSystem=full
PrivateDevices=true
NoNewPrivileges=true
WorkingDirectory=/opt/minecraft/server
ExecStart=/usr/bin/java -Xmx4G -Xms1G -jar minecraft_server.jar nogui
ExecStop=/usr/bin/screen -p 0 -S minecraft -X eval 'stuff "say SERVER SHUTTING DOWN IN 10 SECONDS!"\015'
ExecStop=/bin/sleep 10
ExecStop=/usr/bin/screen -p 0 -S minecraft -X eval 'stuff "save-all"\015'
ExecStop=/usr/bin/screen -p 0 -S minecraft -X eval 'stuff "stop"\015'

[Install]
WantedBy=multi-user.target
```

## Step 8: Start and Enable the Service

```bash
sudo systemctl daemon-reload
sudo systemctl start minecraft
sudo systemctl enable minecraft
```

## Step 9: Open Firewall Port
If you have UFW enabled:

```bash
sudo ufw allow 25565/tcp
```

## Step 10: Check Server Status

```bash
sudo systemctl status minecraft
```

To view the server logs:

```bash
sudo journalctl -u minecraft
```

## Step 11: Configure Port Forwarding
For players to connect from outside your network, configure port forwarding on your router to forward port 25565 to your server's local IP address.

## Step 12: Backup Setup (Recommended)
Create a backup script:

```bash
sudo nano /opt/minecraft/backup.sh
```

Add the following:

```bash
#!/bin/bash
DATE=$(date +%Y-%m-%d_%H-%M-%S)
BACKUP_DIR="/opt/minecraft/backups"
SERVER_DIR="/opt/minecraft/server"

mkdir -p $BACKUP_DIR
systemctl stop minecraft
tar -czf $BACKUP_DIR/minecraft_backup_$DATE.tar.gz -C $SERVER_DIR .
systemctl start minecraft
```

Make it executable:

```bash
sudo chmod +x /opt/minecraft/backup.sh
```

Add it to crontab for automatic daily backups:

```bash
sudo crontab -e
```

Add this line:

```
0 3 * * * /opt/minecraft/backup.sh
```
