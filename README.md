# Dotfiles

> My config files

## Install

1. Auto install: `curl -sL http://df.arthurc.me/setup.sh | sh`
2. Manual install:
   1. Clone this repo: `git clone --recursive https://github.com/arthurc0102/dotfiles.git ~/.dotfiles`.
   2. Run setup script: `sh ~/.dotfiles/setup.sh` or link config file to the right place by yourself.
3. Font: <https://github.com/microsoft/cascadia-code>

## Setup

### Git

Update name and email in `~/.gitconfig.user`

If you need to use multi account add config below to your `.gitconfig.user`

```conf
[includeIf "gitdir:/path/to/work/"]  # The trailing slash is necessary.
  path = ~/.gitconfig.work
```

Example for `.gitconfig.work`

```conf
[core]
  sshCommand = "ssh -o IdentitiesOnly=yes -i ~/.ssh/work.pub"

[user]
  email = work@example.com
  name = Your Name
```

### Pyenv

Install pyenv: `curl https://pyenv.run | bash`

Install python:

```bash
pyenv install 3.9.1  # Or other version
pyenv global 3.9.1  # Or other version
```

### Pipx

> Make sure you have Python3 already.

If you need pipx, run [setup-pipx.sh](./setup-pipx.sh).
Install `argcomplete` for pipx autocomplete: `pipx install argcomplete`.

### Nvm

Install nvm: `git clone git://github.com/nvm-sh/nvm.git ~.nvm`

Install node:

```bash
nvm install --lts
nvm use --lts
```

## Test

- Test startup speed: `/usr/bin/time zsh -i -c exit`
