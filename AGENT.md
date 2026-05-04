# Agent Instructions

## Context
This repository (`dotfiles`) manages personal configuration files. It is heavily utilized by automated provisioning scripts (like Terraform Cloud-Init configurations).

## Structure & Architecture
- **Everything must go inside the `config/` directory.** Do not place configuration files at the root of the repository.
- The `config/` directory in this repo perfectly mirrors the `~/.config/` directory on a target Linux/macOS machine.
- During provisioning, the contents of `config/` are typically copied directly into `~/.config/` using `cp -rT repo/config/ ~/.config/`.

## Configuration Specifics
- **Zsh:**
  - The main configuration file is `config/zsh/.zshrc`.
  - Aliases should be added to `config/zsh/aliases.zsh`, not directly to `.zshrc`. The `aliases.zsh` file is sourced at the bottom of `.zshrc` to override default plugin aliases.
  - The theme is Powerlevel10k. Its configuration is in `config/zsh/p10k.zsh`.
- **Tmux:**
  - Configurations are located in `config/tmux/`.

## Guidelines
- Avoid creating files with duplicate names or outside of the `config/` structure unless it's a repository management file (like `README.md`, `AGENT.md`, `.gitignore`).
- When modifying aliases, strictly edit `aliases.zsh`.
- Do not make unprompted destructive actions or re-architect the dotfiles approach without asking the user for confirmation.