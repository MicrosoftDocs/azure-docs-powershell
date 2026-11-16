---
title: Install the Azure PowerShell preview
description: Learn how to install the Azure PowerShell preview modules.
ms.date: 11/13/2026
---

# Install the Azure PowerShell preview

The Azure PowerShell preview ships as **azps** — the Az PowerShell modules (`Az.*`). The modules require PowerShell 7.6 or later.

> [!NOTE]
> For more information about installing the Azure CLI (`az` command-line tool), see the [Azure CLI preview install overview](/cli/azure/install-overview?view=azure-cli-preview&preserve-view=true).

## Install azps (one command)

The installer downloads the latest public preview bundle from
[GitHub Releases](https://github.com/Azure/azclips/releases). GitHub CLI and GitHub sign-in aren't
required.

**Prerequisites:**

- [PowerShell 7.6+](https://aka.ms/powershell)
- `tar` available on `PATH` to extract the bundle

Run the following command inside PowerShell 7.6 or later (`pwsh`) on Linux, macOS, WSL, or Windows:

```powershell
irm https://raw.githubusercontent.com/Azure/azclips/main/install/azps-install.ps1 -ErrorAction Stop | iex
```

The bootstrap downloads and extracts the bundle into a temporary directory, invokes its
`InstallModule.ps1` helper for the current user, and removes its temporary repository and files
afterward. Installing the preview doesn't change your classic Az installation. New preview versions
can coexist with previously installed preview versions.

For installer parameters or manual/offline installation, see
[Install Azure PowerShell preview modules](./install-powershell-modules.md).

## Verify

Start a new PowerShell session and explicitly load the preview before running Azure cmdlets:

```powershell
Import-Module Az -MinimumVersion 0.1.0 -MaximumVersion 0.1.9999
Get-Module Az | Select-Object Name, Version, Path
```

The output should show `Az` with a version in the `0.1.x` series and its installed path.
`Import-Module Az` without a version constraint loads classic Az when it's installed. Running an
Azure cmdlet without explicitly importing the preview can also autoload classic modules. For details,
see [Switch between classic and preview Azure PowerShell](./switch-azps-versions.md).

## Other install scenarios

| You want to… | Guide |
| --- | --- |
| Install a single module, pin a version, or install machine-wide | [install-powershell-modules.md](./install-powershell-modules.md) |
| Install the Azure CLI preview | [install-overview](/cli/azure/install-overview?view=azure-cli-preview&preserve-view=true) |

## What's in a release

| Category | Files | Platforms | Notes |
| --- | --- | --- | --- |
| Module roll-up | `azps-cmdlets-<version>.tar.gz` | agnostic | Convenience bundle of all PowerShell module packages. |
| PowerShell module packages | `Az.*.nupkg` | agnostic | Install with the bundled `InstallModule.ps1`. Requires PowerShell 7.6+. |
