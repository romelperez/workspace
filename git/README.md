# Git

## Install `git`

```bash
sudo apt-get install git
```

## Configuration

```bash
git config --global user.name "Romel Pérez"
git config --global user.email "ronelprhone@gmail.com"
```

## Bash modifications

### Install `oh-my-zsh`

Follow the instructions in [oh-my-zsh repository](https://github.com/robbyrussell/oh-my-zsh).

### Git enhances

A recommend **oh my zsh**, but if you want some enhaces to Git with your current bash,
then you can add the files:

- `git-prompt.sh`
- `git-completion.bash`

Into you home folder and add the following commands at the end of your `.bashrc` file
located in your home folder:

```bash
# Enable tab completion
source ~/git-completion.bash

# colors!
green="\[\033[0;32m\]"
blue="\[\033[0;34m\]"
purple="\[\033[0;35m\]"
reset="\[\033[0m\]"

# Change command prompt
source ~/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=1
# '\u' adds the name of the current user to the prompt
# '\$(__git_ps1)' adds git-related stuff
# '\W' adds the name of the current directory
export PS1="$purple\u$green\$(__git_ps1)$blue \W $ $reset"
```
