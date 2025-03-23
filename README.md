# The linux family

Linux  
├── Arch-based  
│   ├── Arch Linux  
│   ├── Manjaro  
│   ├── EndeavourOS  
│   ├── Athena OS  `We are here`  
│   ├── Artix Linux  
│   ├── Garuda Linux  
│   ├── ArcoLinux  
│   ├── CachyOS  
│   ├── BlackArch  
│   ├── Parabola GNU/Linux  
│  
├── Debian-based  
│   ├── Debian  
│   ├── Ubuntu  
│   │   ├── Kubuntu  
│   │   ├── Xubuntu  
│   │   ├── Lubuntu  
│   │   ├── Ubuntu MATE  
│   │   ├── Ubuntu Budgie  
│   │   ├── Pop!_OS  
│   │   ├── Zorin OS  
│   │   ├── Linux Mint  
│   ├── Kali Linux  
│   ├── Parrot OS  
│   ├── MX Linux  
│   ├── Devuan  
│  
├── Fedora-based  
│   ├── Fedora  
│   ├── Ultramarine Linux  
│   ├── Nobara  
│   ├── Qubes OS  
│  
├── Other Distros  
│   ├── openSUSE (SUSE-based)  
│   ├── Void Linux (Independent)  
│   ├── Gentoo (Source-based)  
│   ├── Slackware (Oldest still maintained)  
│   ├── Alpine Linux (Security-focused)  
│   ├── Clear Linux (Intel-optimized)  


# Linux Basics

## Introduction
This workshop covers essential Linux commands and concepts necessary for participating in Capture The Flag (CTF) competitions. It's designed for beginners and focuses on practical skills for navigating Linux systems. Tailored specifically for Arch based systems.

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

### Changing mod
- `chmod`: change the mod of any file
 -`chmod +x [filename]` 


### Searching and Filtering and editing text
- `grep`: Search for patterns in files
  - Example: `grep "password" file.txt`
- `find`: Search for files and directories
  - Example: `find . -name "flag.txt"`
- `vim`: Simple text editor
	- Creates a file if the file doesnt exist or else lets you edit it.
	 - Example: `vim sometext.txt` or `vim script.py` 


### Networking commands
- `nc`: Netcat is a versatile networking tool for reading from and writing to network connections using TCP or UDP.
 - `nc [options] [hostname] [port]`
- `wget`: It is used to download files from the web.
 - `wget [URL]`: Download the file from the url.
 - `wget -r [URL]`: Download everyfile from the web recursively from the url. 


### Other Useful Commands
- `file [filename]`: Determine file type
- `strings [filename]`: Extract readable text from binary files
- `tar -xvf [filename]`: Extract tar files
- `gunzip [filename]`: unzip .gz files

### About File Images

A disk image is a huge dump of many numbers. But these numbers have an invisible structure to them that gives them much more meaning. Navigating this invisible structure manually is tedious and deeply difficult, but the Sleuthkit tools handle this invisible structure for us. To begin using the Sleuthkit tools we must understand some of the layers that apply to disk images. The four main layers are: media, block, inode, and filename.

- Media: the media layer tools all are prepended with 'mm' and operate on the disk image with little guidance from the analyst. mmls is a media layer tool that gives us the partition table of the image and key information for delving into the other layers. Media is the lowest level, providing key information to access the deeper layers, but not shedding much light on the data contained in the image.

- Block: the block layer is the second lowest level of the four layers considered here. Block layer tools are prepended with 'blk' in the Sleuthkit. blkcat is a block layer tool that outputs the contents of a single block. The block layer is the numbers of the disk image broken into equal-sized chunks. A single file is likely to contain multiple blocks.

- Inode: the inode layer is the bookkeeping layer of a disk image. It’s like the table of contents, with the chapter numbers being like the inodes, and the pages like the blocks of a file. Inode layer tools are prepended with 'i'. icat is an inode layer tool that outputs a single file based on its inode number.

- Filename: the filename layer is one layer that most any user of a computer actually sees and interacts with. This is the layer with which we will start our exploration of the Sleuthkit in the current challenge. Interacting with the filename layer will look a lot like using the shell normally. Filename layer tools are prepended by 'f'. fls lists the files on an image starting at the root. This is what we will use for our exploration of the disk image.



### Problems: 
Register at `https://play.picoctf.org/`
- https://play.picoctf.org/practice/challenge/85
- https://play.picoctf.org/practice/challenge/320
- https://play.picoctf.org/practice/challenge/15

Disk based questions
 - https://play.picoctf.org/practice/challenge/300 


## CTF Tips
- Always check file permissions and hidden files
- Use `strings` on binary files to find readable text
- Combine commands with pipes (`|`) for efficient searching
- Practice regularly to improve your skills




## Further Resources
- [Linux Command Line Cheat Sheet](https://cheatography.com/davechild/cheat-sheets/linux-command-line/)
- [OverTheWire Bandit Wargame](https://overthewire.org/wargames/bandit/) for practicing Linux skills
- [PicoCTF](https://picoctf.org/) for beginner-friendly CTF challenges

