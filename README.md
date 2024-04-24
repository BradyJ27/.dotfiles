# .dotfiles
[toc]
This repo contains the setup and necessary files for my development setup.

# WSL Setup
In general, just do `wsl --install`. I just use the default version of Ubuntu.

See [here](https://learn.microsoft.com/en-us/windows/wsl/install) for up to date instructions on installing WSL.

- `stty -ixon` to disable \<ctrl\>+s. (For reverse-i search)

# Terminal
I use Windows terminal (get from Microsoft Store).

## Oh-my-posh
[oh-my-posh](https://ohmyposh.dev/) makes the terminal look decent.
## Install
- `sudo apt-get install build-essential`
- Install Homebrew first:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install jandedobbeleer/oh-my-posh/oh-my-posh
test -d ~/.linuxbrew && eval "$(~/.linuxbrew/bin/brew shellenv)"
test -d /home/linuxbrew/.linuxbrew && eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"" >> ~/.bashrc
```
- Install gcc `brew install gcc`
- Install oh-my-posh `brew install jandedobbeleer/oh-my-posh/oh-my-posh`
- `eval "$(oh-my-posh init bash --config $(brew --prefix oh-my-posh)/themes/amro.omp.json)"`

# Languages 
## Python
- `sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget software-properties-common`
- `sudo add-apt-repository ppa:deadsnakes/ppa`
- `sudo apt install python3.12`
- `sudo apt-get install python3-pip`
- `sudo apt-get install python3.12-distutils`

## Nodejs
- `$ curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -`
- `sudo apt-get install nodejs`
- `sudo apt-get install npm`
- `node --version`
- `npm --version`

# Nvim
View my [Nvim repo](https://github.com/BradyJ27/nvim) for specific my specific Nvim config. It is also a submodule here.

## Installing Neovim
I usually just use apt to install neovim from package. See the [neovim readme](https://github.com/neovim/neovim/blob/master/INSTALL.md) for info on how to install. 
`sudo apt-get install neovim`

# Git
## Config Merge Tool
Shoutout to [this post](https://smittie.de/posts/git-mergetool/) for helping this config
- `git config mergetool nvim`
- `git config mergetool.nvim.cmd 'nvim -d -c "wincmd l" -c "norm ]c" "$LOCAL" "$MERGED" "$REMOTE"'`
- Use `[c` and `]c` for next and previous changes
- Type `:diffg LO` or `:diffg RE` to accept Local/Remote changes respectively

