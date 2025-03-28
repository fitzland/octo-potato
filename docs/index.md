# Welcome to fitzhugh.us

## Purpose

This site is used to collect my notes and documentation on various topics.

It is made using mkdocs. For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Workflow for Editing Website

1. Generate SSH Keys (if you don't already have them; I do)

	* Open your preferred terminal (I use alacritty)
	* Run the following command to generate a SSH key pair:
	```bash
	ssh-keygen -t ed25519 -C "your_email@example.com"
	```
		* When prompted, you can accept the default file location (/home/username/.ssh/id_ed22519) by pressing Enter.
		* Choose a strong passphrase for your key and enter it twice when prompted.
		* You don't have to enter a passphrase, but understand that weakens the security of your key.

2. Setup SSH keys with 

### Clone Github Repository

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
