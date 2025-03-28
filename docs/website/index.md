# Website

## Workflow for Editing Website

### 1. Generate SSH Keys (if you don't already have them; I do)

	* Open your preferred terminal (I use `alacritty`)
	* Run the following command to generate a SSH key pair:

	```bash
	ssh-keygen -t ed25519 -C "your_email@example.com"
	```
		* When prompted, you can accept the default file location (`/home/username/.ssh/id_ed22519`) by pressing Enter.
		* Choose a strong passphrase for your key and enter it twice when prompted.
		* You don't have to enter a passphrase, but understand that weakens the security of your key.

### 2. Setup SSH keys with 

