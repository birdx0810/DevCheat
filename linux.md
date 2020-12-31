# Linux Cheat Sheet

## Directory Hierarchy
```
-/: This is the root folder of the Linux directory hierarchy.
    -/bin/: This contains commands used by a regular user.
    -/boot/: The files required for the operating system startup are stored here.
    -/dev/: The device driver files are stored in this folder. These device driver files will point to hardware-related programs running in kernel.
    -/etc/: This folder contains configuration files and startup scripts.
    -/home/: This folder contains a home folder of all users except the administrator.
    -/lib/: The library files are stored in this folder.
    -/media/: External media such as a USB pen drive is mounted in this folder.
    -/opt/: The optional packages are installed in this folder.
    -/proc/: This contains files which give information about kernel and every process running in OS.
    -/root/: This is the administrators home folder.
    -/sbin/: This contains commands used by the administrator or root user.
    -/usr/: This contains secondary programs, libraries, and documentation about user-related programs. 
    -/var/: This contains variable data such as http, tftp, and similar other.
    -/sys/: This dynamically creates the sys files
```

## Basic Commands
| Command | Fucntion | Usage |
| - | - | - |
| man | Get manual for command | `man <command>` |
| whoami | Get the current user | `whoami` |
| pwd | Get the current directory path | `pwd` |
| ls | List the files & directories in path | `ls <path>` |
| cd | Change current directory to path | `cd <path>` |
| mv | Move files | `mv <source> <destination>` |
| cp | Copy files | `cp <source> <destination>` |
| df | List hard disk space usage | `df -h` |
| du | List file/dir size | `du -h` |
| su | Switch user | `su <user>` |

## Getting Started
### debian basic setup
```bash
sudo apt-get update -y && sudo apt-get upgrade -y && sudo apt-get autoremove -y
sudo apt-get install vim gcc htop tmux git curl
sudo apt-get python3-dev python3-pip python3-venv
```

### language
```bash
# fcitx Input Method
sudo apt-get install fcitx fcitx-pinyin
# IBus Input Method (unstable)
sudo apt-get install ibus ibus-pinyin ibus-chewing ibus-mozc
```

### network 
```bash
sudo apt-get install net-tools nmap whois iperf tcpdump
```

### nvidia drivers
```bash
sudo apt search nvidia
sudo ubuntu-drivers devices
sudo apt-get install nvidia-driver-<version>
```

### fish
```bash
sudo apt-add-repository ppa:fish-shell/release-3
sudo apt-get update
sudo apt-get install fish
curl -L https://get.oh-my.fish | fish

chsh -s $(which fish)

# Install nvm for fish
omf install nvm
fish_config
```

### vimrc
```bash
git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime
sh ~/.vim_runtime/install_awesome_vimrc.sh
```

### steam
```bash
# Install prerequisites
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libgl1-mesa-glx:i386 -y
# Download the steam_latest.deb installer from 
# https://store.steampowered.com/about/
sudo apt-get install ./steam_latest.deb
```

