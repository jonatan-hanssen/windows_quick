# Windows setup

## Tastatur

* Last ned [MSKLC](https://www.microsoft.com/en-us/download/details.aspx?id=102134)
    * Installer [ColemakJK](./colemak_jk.klc)
* Last ned powertoys
    * Remap caps lock til escape
* Regedit
    * Gå til HKEY_CURRENT_USER/Control Panel/Keyboard
        * Sett KeyboardDelay til 2
        * Sett KeyboardSpeed til 13

## WSL

* Last ned wsl
* Powershell -> wsl --install archlinux

```
passwd
pacman -Syu
exit

wsl --terminate archlinux
wsl -d archlinux

pacman -S sudo base-devel neovim sway zsh exa ranger firefox python git npm nodejs tree-sitter tree-sitter-cli 
useradd -m jona
passwd jona
usermod -aG wheel jona
EDITOR=nvim visudo
// uncomment %wheel ALL=(ALL:ALL) ALL
sudo nvim /etc/wsl.conf
// legg inn
// [user]
// default = jona
// [network]
// hostname = archlinux
// [interop]
// appendWindowsPath = false
chsh -s /usr/bin/zsh
echo "ZDOTDIR=/home/jona/.config/zsh" >> .zshenv
git clone https://github.com/jonatan-hanssen/config.git
mv config .config
mkdir -p .cache/zsh
exit

wsl ~ -d archlinux

sudo nvim /etc/locale.gen
locale-gen
cd .local/share/nvim/lazy/coc.nvim
npm ci

pac alacritty ttf-jetbrains-mono-nerd ttf-jetbrains-mono ttf-font-awesome sway waybar swaylock swayidle swaybg python-i3ipc xorg-xwayland catimg

git clone https://github.com/jordankoehn/sway-wsl2.git
cd sway-wsl2
sh install.sh

start-sway
```

## Om windows bound

- Last ned GlazeWM
- Last ned alacritty på windows
- Last ned Jetbrains Mono Nerd Font
