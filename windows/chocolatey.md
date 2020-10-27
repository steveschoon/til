# Chocolatey

### Installing

- Open PowerShell Prompt
- Execute `Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))`

### Useful Commands

- What's installed: `choco list -l`

### Favorite Packages
- Git:  `choco install git`
- Vim: `choco install vim`
