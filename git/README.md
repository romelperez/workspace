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

## SSH key

Copy the ssh files `id_rsa` and `id_rsa.pub` into another computer and enforce permissions:

```bash
chown romelperez:romelperez ~/.ssh/id_rsa*
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
```

Or [generated a new SSH key and added it to the ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) and [add the SSH key to GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/#platform-linux) or any git provider.

Remember the repositories should have the origin set with ssh.

Check with:

```bash
git remote show origin
```

To change it:

```bash
git remote set-url origin git+ssh://git@github.com/romelperez/workspace.git
```

That was an example of this repository.

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
