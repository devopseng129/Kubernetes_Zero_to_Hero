# Install Docker Desktop
**Download from**: https://www.docker.com/products/docker-desktop/
```bash
docker --version
docker ps
```

# Install Chocolatey (Windows)
**search for PowerShell, Run as Administrator**
Check Execution Policy
```bash
Get-ExecutionPolicy
```
If it shows: Restricted
```bash
Set-ExecutionPolicy Bypass -Scope Process -Force
```

# Install Chocolatey:
```bash
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = `
[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Verify Installation: Close PowerShell and open a new terminal.
```bash
choco --version
```

#Install kubectl Using Chocolatey
```bash
choco install kubernetes-cli -y
kubectl version --client
```

# Install Kind Using Chocolatey
```bash
choco install kind -y
kind version
```

# Create Cluster
```bash
kind create cluster --name k8s-zero-to-hero
kubectl get nodes
```