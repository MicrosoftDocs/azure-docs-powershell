---
title: Install the Azure PowerShell preview release
description: Learn how to install the Az PowerShell modules from the Azure PowerShell preview release.
---

# Install the Azure PowerShell preview release

> This page covers **azps** (the Az PowerShell modules) — a separate product from azcli. For the CLI, see the [Azure CLI preview install overview](/cli/azure/install-overview?view=azure-cli-preview).

The Az PowerShell cmdlets ship as NuGet module packages (`Az.*.nupkg`). Each release includes `azps-cmdlets-<version>.tar.gz`, which contains:

- the `Az.<version>.nupkg` roll-up (meta) package,
- every `Az.*` dependency package it requires,
- an `InstallModule.ps1` helper, and
- `NOTICE` / `LICENSE`.

## Requirements

| Requirement | Why |
| --- | --- |
| **PowerShell 7.6 or later** | The binary cmdlets are built on `System.Management.Automation` 7.6 (.NET 10). PowerShell 7.5 and Windows PowerShell 5.1 cannot load them. |

Check your version with `$PSVersionTable.PSVersion`. Install or update PowerShell from <https://aka.ms/powershell> if needed.

## Install with the bundled script

All steps below run in **PowerShell 7.6+**.

Download the bundle from the latest release using your authenticated GitHub CLI (`gh`), which works on the private repo. (Or download `azps-cmdlets-<version>.tar.gz` manually from the repo's [GitHub Releases](https://github.com/Azure/azclips/releases) page.)

```powershell
gh release download --repo Azure/azclips --pattern 'azps-cmdlets-*.tar.gz' --dir . --clobber
```

Extract it:

```powershell
New-Item -ItemType Directory -Force -Path azps-cmdlets | Out-Null
$bundle = Get-ChildItem azps-cmdlets-*.tar.gz | Sort-Object LastWriteTime -Descending | Select-Object -First 1
tar -xzf $bundle.FullName -C azps-cmdlets
```

Install it (registers the extracted folder as a temporary local repository and installs the `Az` roll-up and all `Az.*` dependencies for the current user):

```powershell
./azps-cmdlets/InstallModule.ps1
```

### Script options

| Parameter | Default | Purpose |
| --- | --- | --- |
| `-ModuleName` | `Az` | Install a single module instead of the roll-up, e.g. `-ModuleName Az.Compute`. |
| `-RequiredVersion` | inferred from `Az.<version>.nupkg` | Pin a specific version. |
| `-Scope` | `CurrentUser` | Use `AllUsers` for a machine-wide install (needs elevation). |
| `-RepositoryName` | `LocalAzclips` | Name of the temporary local PSRepository. |

Example — install just the Compute module for all users:

```powershell
./azps-cmdlets/InstallModule.ps1 -ModuleName Az.Compute -Scope AllUsers
```

## Verify

```powershell
Import-Module Az
Get-Module Az.* -ListAvailable | Select-Object Name, Version
```

The `Az.*` modules should be listed. Cmdlets that contact Azure require sign-in (`Connect-AzAccount`) and a subscription — being prompted to authenticate means the install itself is working.

## Troubleshooting

| Symptom | Fix |
| --- | --- |
| Module fails to import / load error | Confirm PowerShell 7.6+ (`$PSVersionTable.PSVersion`). 7.5 and 5.1 cannot load these cmdlets. |
| `Register-PSRepository` says the repo already exists | Run `Unregister-PSRepository -Name LocalAzclips`, then retry (the bundled script does this automatically). |
| `Install-Module` cannot find the module | Run it from the extracted `azps-cmdlets` folder, or pass the correct `-Repository`/`SourceLocation` path. |
| Command conflicts with an existing Az install | Open a fresh PowerShell session, or use `-AllowClobber`. |
| Need a machine-wide install | Use `-Scope AllUsers` from an elevated PowerShell session. |
