# dotfiles
Arquivos de configurações de ferramentas


## Linux

1. Instalar Zsh
2. Instalar Oh-my-zsh!
3. Instalar JetBrainsMono Nerd Font
4. Instalar Tema Powerlevel10k:
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
```
5. Instalar Kitty Terminal, temas e configurações:
```
curl -L https://sw.kovidgoyal.net/kitty/installer.sh | sh /dev/stdin
sudo ln -s ~/.local/kitty.app/bin/kitty /usr/bin/kitty
sudo ln -s ~/.local/kitty.app/share/applications/kitty.desktop /usr/share/applications/kitty.desktop
sudo ln -s ~/.local/kitty.app/share/icons/hicolor/256x256/apps/kitty.png /usr/share/icons
gsettings set org.gnome.desktop.default-applications.terminal exec kitty
gsettings set org.gnome.desktop.default-applications.terminal exec-arg ''
git clone --depth 1 https://github.com/dexpota/kitty-themes.git ~/.config/kitty/kitty-themes
ln -s ~/.config/kitty/kitty-themes/themes/Darkside.conf ~/.config/kitty/theme.conf
cd ~
git clone https://github.com/xaxim/dotfiles.git
ln -s ~/dotfiles/linux/kitty.conf ~/.config/kitty/kitty.conf
```
6. Instalar pasta de shell scripts:
```
ln -s ~/dotfiles/linux/bin/ ~/bin/
```


#### History real:
```
git clone --depth 1 https://github.com/ryanoasis/nerd-fonts

cd ~/.local/share/fonts
fc-cache -fv

kitty + list-fonts --psnames | grep 'JetBrainsMono'

sudo touch /usr/share/applications/STS.desktop

git clone https://github.com/vinceliuice/grub2-themes.git
cd grub2-themes
sudo ./install.sh -b -s
code /etc/default/grub
sudo grub-mkconfig -o /boot/grub/grub.cfg

sudo apt install libsecret-1-0 libsecret-1-dev
cd /usr/share/doc/git/contrib/credential/libsecret
sudo make
git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret
```