
# Terminal Emulator
 Use Catpuccino Mocha theme.

# Tmux Setup Notes

## Config
  Use the .tmux.conf in the repo, put it in ~/
##  Install TPM

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Then inside a running tmux session:
1. Source your config: `tmux source ~/.tmux.conf`
2. Install all plugins: press `prefix + I` (capital I) — default prefix is `Ctrl+b`

## Verify Installation

```bash
ls ~/.tmux/plugins/   # should show all plugin folders after prefix+I
```
