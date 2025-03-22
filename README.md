# Linux Basics and Forensics

## Introduction
This workshop covers essential Linux commands and concepts necessary for participating in Capture The Flag (CTF) competitions. It's designed for beginners and focuses on practical skills for navigating Linux systems and performing basic forensics tasks.

## Linux File System Structure
Linux uses a hierarchical file system structure. Key directories include:

- `/` (root): The top-level directory
- `/home`: User home directories
- `/etc`: System configuration files
- `/bin` and `/sbin`: Essential system binaries
- `/usr`: User utilities and applications
- `/var`: Variable data (logs, temp files)
- `/tmp`: Temporary files

## Essential Linux Commands

### Inbuilt manual
- `man [command_name]`: Gives the description of a command and how to use it

### Package manager
- `Update`: pacman -Syu
	- `Note`: Compatible with paru and yay which are AUR helpers
- `Update Mirrors`: pacman -Syy
	- `Note` : Used when your downloads are too slow, it means you have to update your mirrors
- `Installing a package`: pacman -S [package_name]
- `Deleting a package`: pacman -Rns [package_name]
- `Removing Cache`: pacman -Scc
	- Do it once in a while 

### Navigation and File Management
- `pwd`: Print working directory
- `ls`: List files and directories
  - Options: `-l` (long format), `-a` (show hidden files)
- `cd`: Change directory
  - `cd ..` to go up one level, `cd ~` to go to home directory
- `mkdir`: Create a new directory
- `touch`: Create an empty file or update timestamps
- `cp`: Copy files or directories
- `mv`: Move or rename files or directories
- `rm`: Remove files or directories
  - Use `-r` for directories, but be cautious!

### Viewing File Contents
- `cat`: Display entire file content
- `head`: Show the beginning of a file
- `tail`: Show the end of a file
- `less`: View file contents page by page

### File Permissions
- `chmod`: Change file permissions
  - Example: `chmod 777 file.txt`

### Searching and Filtering and editing text
- `grep`: Search for patterns in files
  - Example: `grep "password" file.txt`
- `find`: Search for files and directories
  - Example: `find . -name "flag.txt"`
- `vim`: Simple text editor
	- Creates a file if the file doesnt exist or else lets you edit it.
	 - Example: `vim sometext.txt` or `vim script.py` 



### Other Useful Commands
- `file [filename]`: Determine file type
- `strings [filename]`: Extract readable text from binary files
- `tar -xvf [filename]`: Extract tar files
- `gunzip [filename]`: unzip .gz files



## CTF Tips
- Always check file permissions and hidden files
- Use `strings` on binary files to find readable text
- Combine commands with pipes (`|`) for efficient searching
- Practice regularly to improve your skills




## Further Resources
- [Linux Command Line Cheat Sheet](https://cheatography.com/davechild/cheat-sheets/linux-command-line/)
- [OverTheWire Bandit Wargame](https://overthewire.org/wargames/bandit/) for practicing Linux skills
- [PicoCTF](https://picoctf.org/) for beginner-friendly CTF challenges

