# dotfiles
A better $HOME, for me.
Install oh my zsh first.

# Making the repo

```
 git init --bare $HOME/dotfiles
 git clone git@github.com:xevansz/dots.git tmpdotfiles
 rsync --recursive --verbose --exclude '.git' tmpdotfiles/ $HOME
 rm -r tmpdotfiles

 ln -s ~/.config/shell/profile  .zprofile
 rm ~/.zshrc ~/.zsh_history
 rm ~/.oh-my-zsh

 alias dots='/usr/bin/git --git-dir=$HOME/dotfiles/ --work-tree=$HOME'
 
 git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
 git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting 

```

# Setup
```
dots config --local status.showUntrackedFiles no
dots remote add origin https://github.com/xevansz/dots
dots status
```
