
### 
```bash
sudo apt-get update  
sudo apt-get upgrade
sudo apt-get install vim gcc htop openssh-server python3-dev python3-pip python3-venv tmux git curl
```

### nvidia drivers
```bash
sudo apt search nvidia
sudo ubuntu-drivers devices
sudo apt-get install nvidia-driver-<version>
```

### zsh
```bash
sudo apt-get install zsh
chsh -s $(which zsh)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### fish
```bash
sudo apt-add-repository ppa:fish-shell/release-3
sudo apt-get update
sudo apt-get install fish
curl -L https://get.oh-my.fish | fish

# Install nvm for fish
omf install nvm
fish_config
```

### vimrc
```bash
git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime
sh ~/.vim_runtime/install_awesome_vimrc.sh
```

### Logical Volume Group (磁區組)
```
pvdisplay
pvcreate /dev/sda1 /dev/sdb1
pvs
vgcreate -s 16M vg_home /dev/sda1 /dev/sdb1
vgdisplay --units b
lvcreate -L 3000571527168b -n lv_home vg_home
```