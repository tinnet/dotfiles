# dotfiles

My dotfiles, managed with [chezmoi](https://www.chezmoi.io/).

## Setup on a new machine

1. **Install mise** (dev tool manager):
   ```sh
   curl https://mise.run | sh
   ```

2. **Clone dotfiles & apply**:
   ```sh
   mise exec chezmoi -- chezmoi init --apply tinnet/dotfiles
   ```
   This clones the repo, generates config, applies all dotfiles, and
   automatically installs gitleaks + lefthook inside the repo (via `mise
   install`) and sets up the pre-commit hook.

3. **Install global tools**:
   ```sh
   mise install
   ```
   Now that the global mise config (`~/.config/mise/config.toml`) is in
   place, this installs all the other tools defined there.

## What's included

- **gitleaks** + **lefthook** — pre-commit hook that scans staged files for secrets before every commit
- Shell config (zsh, aliases, zprofile)
- Global tool management via mise (`~/.config/mise/config.toml`)
