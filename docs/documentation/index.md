# Website

## Workflow for Editing Website

### 1. Generate SSH Keys (if you don't already have them; I do)

	* Open your preferred terminal (I use `alacritty`)
	* Run the following command to generate a SSH key pair:

	`ssh-keygen -t ed25519 -C "your_email@example.com"`

		* When prompted, you can accept the default file location (`/home/username/.ssh/id_ed22519`) by pressing Enter.
		* Choose a strong passphrase for your key and enter it twice when prompted.
		* You don't have to enter a passphrase, but understand that weakens the security of your key.

### 2. Start the ssh-agent

	* Make sure the ssh-agent is running with the following command:

	`eval "$(ssh-agent -s)"` 

	This will start the agent and print its process ID (PID).

### 3. Add your SSH key to the ssh-agent

	* If you used the default filename, you would issue this command:

	`ssh-add ~/.ssh/id_ed25519`

### 4. Add the Public Key to Github

	* You should be prompted for a passphrase if you set one.
	* Add to GitHub:
		1. Go to your GitHub account on the web (github.com).
		2. Click on your profile picture in the upper-right corner and select "Settings".
		3. In the left sidebar, click "SSH and GPG keys".
		4. Click "New SSH key" or "Add SSH key".
		5. Give the key a descriptive title (e.g., "My Debian PC").
		6. Paste the public key you copied into the "Key" field.
		7. Click "Add SSH key". You may be prompted to confirm your password.

### 5. Test the SSH Connection to Github

	* Verify that GitHub recognizes your key:

	`ssh -T git@github.com`

	* You should see a message like:

	`Hi yourusername! You've successfully authenticated, but GitHub does not provide shell access.`

	* Replace yourusername with your actual GitHub username. 

### 6. Clone your MkDocs Repository

	* Go to your repository on GitHub in your web browser.
	* Click the green "Code" button.
	* Select the "SSH" tab. You should see a URL that starts with git@github.com:.
	* Copy that SSH URL (e.g., git@github.com:yourusername/your-mkdocs-repo.git).
	* In your terminal, navigate to the directory where you want to store your MkDocs project.
	* Clone the repository:

	`git clone git@github.com:yourusername/your-mkdocs-repo.git`

	* Replace git@github.com:yourusername/your-mkdocs-repo.git with the actual SSH URL you copied.

### 7. Edit your MkDocs Documents

	* Navigate into the cloned repository:

	`cd your-mkdocs-repo`

	* Edit your files using Micro text editor:

	`micro docs/index.md`

### 8. Commit and Push Changes

	* Check the Status: See what files have changed:

	`git status`

	* This will show you which files have been modified.

	* Stage Changes: Add the files you want to commit to the staging area:

	`git add .          # Adds all modified files in the current directory and subdirectories`

	* Using `git add .` is generally fine if you want to commit all your changes, but be careful if you have temporary or auto-generated files that you don't want to track.

	* Commit Changes: Create a commit with a descriptive message:

	`git commit -m "Update index page with new content"`

	* Replace "Update index page with new content" with a meaningful message describing the changes you made.

	* Push Changes: Upload your commits to the remote repository on GitHub:

	`git push origin master`

	* origin is usually the name of the remote repository (GitHub, in this case).

	* main (or master if your repository hasn't been updated) is the name of the branch you're pushing to.

That's basically it.
