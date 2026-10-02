---
title: Install the Azure PowerShell preview
description: Learn how to install the Azure PowerShell preview modules.
---

# Install the Azure PowerShell preview

The Azure PowerShell preview ships as **azps** — the Az PowerShell modules (`Az.*`). The modules require PowerShell 7.6 or later.

> [!NOTE]
> For the Azure CLI (`az` command-line tool), see the [Azure CLI preview install overview](/cli/azure/install-overview?view=azure-cli-preview).

## Install azps (one command)

Preview artifacts live in a **private** GitHub repo; your account has **read** access. The installer uses your authenticated GitHub CLI (`gh`) session.

**Prerequisites:**

- [PowerShell 7.6+](https://aka.ms/powershell)
- [GitHub CLI](https://cli.github.com/) signed in (`gh auth login`)

**Download and install:**

```powershell
gh release download --repo Azure/azclips --pattern 'azps-cmdlets-*.tar.gz' --dir . --clobber
New-Item -ItemType Directory -Force -Path azps-cmdlets | Out-Null
$bundle = Get-ChildItem azps-cmdlets-*.tar.gz | Sort-Object LastWriteTime -Descending | Select-Object -First 1
tar -xzf $bundle.FullName -C azps-cmdlets
./azps-cmdlets/InstallModule.ps1
```

## Verify

```powershell
Import-Module -Name Az
Get-Module -Name Az.* -ListAvailable | Select-Object Name, Version
```

## Other install scenarios

| You want to… | Guide |
| --- | --- |
| Install a single module, pin a version, or install machine-wide | [install-powershell-modules.md](./install-powershell-modules.md) |
| Install the Azure CLI preview | [install-overview](/cli/azure/install-overview?view=azure-cli-preview) |

## What's in a release

| Category | Files | Platforms | Notes |
| --- | --- | --- | --- |
| Module roll-up | `azps-cmdlets-<version>.tar.gz` | agnostic | Convenience bundle of all PowerShell module packages. |
| PowerShell module packages | `Az.*.nupkg` | agnostic | Install with the bundled `InstallModule.ps1`. Requires PowerShell 7.6+. |
