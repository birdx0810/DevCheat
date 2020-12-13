# Linux Cheat Sheet
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
sudo dpkg --add-architecture i386
sudo apt-get update
sudo apt-get install libgl1-mesa-glx:i386 -y
sudo apt-get install ./steam_latest.deb 
```

