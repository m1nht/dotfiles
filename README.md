# Dotfiles

If you're seeing this README file in your home directory, congratulations! Your
home directory is actually a dotfile (git) repo.

Heavily based on [this guide](https://www.atlassian.com/git/tutorials/dotfiles).

## Setup

### 1. Alias

This alias command is very important for interacting with the dotfile repo.

```shell
alias tod='/usr/bin/env git --git-dir=$HOME/.dotfiles --work-tree=$HOME'
```

It's basically a wrapper for the git command, so you can do things like `tod
status` or `tod add <file>` to add new files. You'll want to stick this in your
`.bashrc` or `.bash_aliases` or whatever.


**Warning**: Be careful not to run `tod add -A` (if that's something you're
used to, like me) because that will attempt to add *all* the files in your home
directory to the repo (something you probably don't want).

### 2. Clone


```
$ git clone --bare https://github.com/m1nht/dotfiles $HOME/.dotfiles
$ tod checkout
```

### 3. Custom prompt and more!

Add this line to your `.bashrc` (or equivalent) to use the custom prompt:

```shell
[ -r $HOME/.bash-prompt.sh ] && . $HOME/.bash-prompt.sh
```
