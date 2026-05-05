# Terminal Emulator
 Use Catpuccino Mocha theme.
# For ps1
## Basic for bash, refer to .bashrc for git branch version
export PS1="\e[48;5;183m\e[38;5;235m \u \e[48;5;110m\e[38;5;183m\e[38;5;235m \h \e[48;5;115m\e[38;5;110m\e[38;5;235m \w \e[0m\e[38;5;115m$ " 
## For powershell
notepad $PROFILE
Paste
```shell
function Get-GitBranch {
     $branch = git branch 2>$null | Where-Object { $_ -match '^\*' } | ForEach-Object { $_ -replace '^\* ', '' }
     if ($branch) { return " $branch " }
 }

 function prompt {
     $user    = $env:USERNAME
     $host_   = $env:COMPUTERNAME
     $path    = $executionContext.SessionState.Path.CurrentLocation

     Write-Host " $user " -BackgroundColor Magenta  -ForegroundColor DarkGray -NoNewline
     Write-Host " $host_ " -BackgroundColor Blue     -ForegroundColor DarkGray -NoNewline
     Write-Host " $path " -BackgroundColor DarkGreen -ForegroundColor DarkGray -NoNewline

     $branch = Get-GitBranch
     if ($branch) {
         Write-Host $branch -BackgroundColor DarkYellow -ForegroundColor DarkGray -NoNewline
     }
  
 }
```
# Bash
Use ble.sh

```bash
cd
git clone --recursive --depth 1 --shallow-submodules https://github.com/akinomyoga/ble.sh.git
make -C ble.sh install PREFIX=~/.local
```

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
