# Oh My Posh Personal Theme

My personal Oh My Posh configuration for a consistent terminal experience across different environments.

## Prerequisites

- [Oh My Posh](https://ohmyposh.dev/docs/installation/windows) installed
- [Nerd Font](https://ohmyposh.dev/docs/installation/fonts) installed (e.g., MesloLGS NF)

## Installation

### Ubuntu / WSL (Bash)

Add the following to your `~/.bashrc`:

```bash
export PATH="$HOME/.local/bin:$PATH"

# Only load oh-my-posh via SSH or VS Code (avoids broken characters on TTY console)
if [ -n "$SSH_CONNECTION" ] || [ "$TERM_PROGRAM" = "vscode" ]; then
    eval "$(oh-my-posh init bash --config https://raw.githubusercontent.com/nihanthabala/oh-my-posh-personal/main/mytheme.omp.json)"
fi
```

Then reload:

```bash
source ~/.bashrc
```

### Windows (PowerShell)

Edit your PowerShell profile:

```powershell
notepad $PROFILE
```

Add the following:

```powershell
oh-my-posh init pwsh --config 'https://raw.githubusercontent.com/nihanthabala/oh-my-posh-personal/main/mytheme.omp.json' | Invoke-Expression
```

Then reload:

```powershell
. $PROFILE
```

### VS Code Terminal Font

Add to your VS Code `settings.json`:

```json
{
    "terminal.integrated.fontFamily": "MesloLGS NF"
}
```

## Clearing Cache

To refresh the theme after updates:

```bash
oh-my-posh cache clear
```

## Resources

- [Video Guide](https://www.youtube.com/watch?v=NaHgtHnOPi8)
- [Oh My Posh Documentation](https://ohmyposh.dev/docs/)
