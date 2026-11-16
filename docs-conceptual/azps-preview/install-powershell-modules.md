---
title: Install the Azure PowerShell preview release
description: Learn how to install the Az PowerShell modules from the Azure PowerShell preview release.
ms.date: 11/13/2026
---

# Install the Azure PowerShell preview release

> This article covers **azps** (the Az PowerShell preview modules), a separate product from **azcli** (the Azure CLI preview). For more information about installing the CLI, see the [Azure CLI preview install overview](/cli/azure/install-overview?view=azure-cli-preview&preserve-view=true).

The Az PowerShell cmdlets ship as NuGet module packages (`Az.*.nupkg`). Each release includes `azps-cmdlets-<version>.tar.gz`, which contains:

- the `Az.<version>.nupkg` roll-up (meta) package,
- every `Az.*` dependency package it requires,
- an `InstallModule.ps1` helper, and
- `NOTICE` / `LICENSE`.

## Requirements

| Requirement | Why |
| --- | --- |
| **PowerShell 7.6 or later** | The binary cmdlets are built on `System.Management.Automation` 7.6 (.NET 10). PowerShell 7.5 and Windows PowerShell 5.1 cannot load them. |
| **`tar` available on `PATH`** | Extracts the release bundle on Linux, macOS, WSL, and Windows. |

Check your version with `$PSVersionTable.PSVersion`. Install or update PowerShell from <https://aka.ms/powershell> if needed.

## Install with the bootstrap

All steps below run in **PowerShell 7.6 or later** (`pwsh`) on Linux, macOS, WSL, or Windows.

The bootstrap downloads the latest public preview bundle and invokes its `InstallModule.ps1` helper.
GitHub CLI and GitHub sign-in aren't required.

```powershell
irm https://raw.githubusercontent.com/Azure/azclips/main/install/azps-install.ps1 -ErrorAction Stop | iex
```

By default, it installs the `Az` roll-up and its dependencies for the current user. It uses a unique
temporary local PSRepository and removes that repository and its downloaded and extracted files
afterward. Classic Az isn't changed, and new preview versions can coexist with older preview versions.

### Download and run with parameters

To inspect the script or pass installer parameters, download it first:

```powershell
Invoke-WebRequest `
    https://raw.githubusercontent.com/Azure/azclips/main/install/azps-install.ps1 `
    -OutFile ./azps-install.ps1 -ErrorAction Stop
```

After a successful download, review the script, then run `./azps-install.ps1` with the parameters you
need:

| Parameter | Default | Purpose |
| --- | --- | --- |
| `-ModuleName` | `Az` | Install a single module instead of the roll-up, e.g. `-ModuleName Az.Compute`. |
| `-RequiredVersion` | Highest packaged version of the selected module | Pin a module version available in the downloaded bundle. |
| `-Scope` | `CurrentUser` | Use `AllUsers` for a machine-wide install (needs elevation). |
| `-RepositoryName` | Unique `AzclipsInstall-...` name | Name of the temporary local PSRepository; must not already exist. |

For example, install just the Compute module for all users:

```powershell
./azps-install.ps1 -ModuleName Az.Compute -Scope AllUsers
```

`-RequiredVersion` is a module version, not a GitHub release tag. The bootstrap always downloads the
latest release; it doesn't select an older release when you specify a version. To install a version
from an older release, use the manual workflow.

## Manual or offline installation

Download `azps-cmdlets-<version>.tar.gz` from
[GitHub Releases](https://github.com/Azure/azclips/releases). For an offline machine, transfer the
bundle to that machine. Use a fresh extraction directory for each release, and replace `<version>`
with the version in the downloaded filename:

```powershell
New-Item -ItemType Directory -Path azps-cmdlets | Out-Null
$bundle = Get-Item ./azps-cmdlets-<version>.tar.gz
tar -xzf $bundle.FullName -C azps-cmdlets
if ($LASTEXITCODE -ne 0) { throw 'PowerShell bundle extraction failed.' }
./azps-cmdlets/InstallModule.ps1
```

The bundled helper accepts the same module/version/scope parameters, but its repository-name default
is `LocalAzclips`. It replaces a registered repository with the same name, so use an unused
`-RepositoryName` if you need to preserve an existing repository. After installation, unregister the
repository before removing the extracted directory:

```powershell
Unregister-PSRepository -Name LocalAzclips
```

If you specified a different repository name, use that name instead.

## Verify

Start a new PowerShell session and explicitly load the preview before running Azure cmdlets:

```powershell
Import-Module Az -MinimumVersion 0.1.0 -MaximumVersion 0.1.9999
Get-Module Az | Select-Object Name, Version, Path
```

The output should show `Az` with a version in the `0.1.x` series and its installed path.
`Get-Module Az -ListAvailable` lists installed versions; without `-ListAvailable`, `Get-Module` shows
the module loaded in this session. If you installed only one module, import and check that module
instead of `Az`, using the same version constraints.

Without a version constraint, `Import-Module Az` loads classic Az when it's installed. Running an
Azure cmdlet before explicitly importing the preview can also autoload classic modules. Start a new
session to switch versions; see
[Switch between classic and preview Azure PowerShell](./switch-azps-versions.md).
Cmdlets that contact Azure require sign-in with `Connect-AzAccount` and an appropriate subscription.

## Troubleshooting

| Symptom | Fix |
| --- | --- |
| Module fails to import / load error | Confirm PowerShell 7.6+ (`$PSVersionTable.PSVersion`). 7.5 and 5.1 cannot load these cmdlets. |
| `tar` isn't found or extraction fails | Confirm `tar` is on `PATH` with `Get-Command tar`. For a manual download, download the bundle again and extract it into a fresh directory. |
| Release lookup returns HTTP 403 or 429 | Check GitHub's response for an API rate limit; retry after it resets, or download the bundle manually from GitHub Releases. |
| Bootstrap says the repository already exists | Choose a different `-RepositoryName`; the bootstrap doesn't replace existing repositories. |
| `Install-Module` cannot find the module or version | Confirm the selected module's `.nupkg` is in the downloaded bundle. `-RequiredVersion` must match a packaged module version, not a release tag; use the manual workflow for an older release. |
| Classic modules load or an assembly is already loaded | Start a new PowerShell session and explicitly import the preview with the version range shown above before running Azure cmdlets. `-AllowClobber` doesn't switch loaded module versions. |
| Need a machine-wide install | Use `-Scope AllUsers` from an elevated PowerShell session. |
