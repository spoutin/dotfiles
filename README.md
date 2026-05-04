# Dotfiles

This repository contains my personal configuration files (dotfiles), primarily focusing on Zsh, Tmux, and Neovim.

## Structure

All configurations are stored within the `config/` directory. This is designed to be cleanly mapped to the user's `~/.config/` directory.

- `config/zsh/`: Contains Zsh configurations, including `.zshrc`, `aliases.zsh`, `p10k.zsh` for the Powerlevel10k theme, and other plugin configs.
- `config/tmux/`: Contains Tmux configurations.

## Installation

This repository is designed to be cloned and copied directly into the `~/.config/` directory.

For example, using `cp`:
```bash
git clone https://github.com/spoutin/dotfiles.git ~/dotfiles
mkdir -p ~/.config
cp -rT ~/dotfiles/config/ ~/.config/
```

### Note on Zsh and XDG_CONFIG_HOME
To ensure Zsh looks for `.zshrc` in `~/.config/zsh/`, your `/etc/zshenv` or `~/.zshenv` should contain the following:

```bash
if [[ -z "$XDG_CONFIG_HOME" ]]
then
        export XDG_CONFIG_HOME="$HOME/.config/"
fi

if [[ -d "$XDG_CONFIG_HOME/zsh" ]]
then
        export ZDOTDIR="$XDG_CONFIG_HOME/zsh/"
fi
```