---
title: Uninstall Azure PowerShell
description: How to perform a complete uninstall of Azure PowerShell
ms.date: 12/13/2018
author: sptramer
ms.author: sttramer
ms.manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
---
# Uninstall the Azure PowerShell module

This article tells you how to uninstall an older version of Azure PowerShell, or completely remove it from
your system. If you've decided to completely uninstall the Azure PowerShell, give us some feedback
through the [Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet.
If you encounter a bug, we'd appreciate it if you [file a GitHub issue](https://github.com/azure/azure-powershell/issues).

## Uninstall the Az module

To uninstall the Az modules, use the
[Uninstall-Module](/powershell/module/powershellget/uninstall-module) cmdlet. However,
`Uninstall-Module` only uninstalls one module. To remove Azure PowerShell completely, you must
uninstall each module individually. Uninstallation can be complicated if you have more than one version of Azure
PowerShell installed.

To check which versions of Azure PowerShell you currently have installed, run the following command:

```powershell-interactive
Get-InstalledModule -Name Az -AllVersions
```

```output
Version             Name                           Repository           Description
-------             ----                           ----------           -----------
0.7.0               Az                             PSGallery            Azure Resource Manager Module
1.0.0               Az                             PSGallery            Azure Resource Manager Module
```

The following script queries the PowerShell Gallery to get a list of dependent submodules. Then, the script
uninstalls the correct version of each submodule. You will need to have administrator access to run this script
in a scope other than `Process` or `CurrentUser`.

```powershell-interactive
function Uninstall-AllModules {
  param(
    [Parameter(Mandatory=$true)]
    [string]$TargetModule,

    [Parameter(Mandatory=$true)]
    [string]$Version,

    [switch]$Force,

    [switch]$WhatIf
  )
  
  $AllModules = @()
  
  'Creating list of dependencies...'
  $target = Find-Module $TargetModule -RequiredVersion $version
  $target.Dependencies | ForEach-Object {
    if ($_.requiredVersion) {
      $AllModules += New-Object -TypeName psobject -Property @{name=$_.name; version=$_.requiredVersion}
    }
    else { # Assume minimum version
      # Minimum version actually reports the installed dependency
      # which is used, not the actual "minimum dependency." Check to
      # see if the requested version was installed as a dependency earlier.
      $candidate = Get-InstalledModule $_.name -RequiredVersion $version
      if ($candidate) {
        $AllModules += New-Object -TypeName psobject -Property @{name=$_.name; version=$version}
      }
      else {
        Write-Warning ("Could not find uninstall candidate for {0}:{1} - module may require manual uninstall" -f $_.name,$version)
      }
    }
  }
  $AllModules += New-Object -TypeName psobject -Property @{name=$TargetModule; version=$Version}

  foreach ($module in $AllModules) {
    Write-Host ('Uninstalling {0} version {1}...' -f $module.name,$module.version)
    try {
      Uninstall-Module -Name $module.name -RequiredVersion $module.version -Force:$Force -ErrorAction Stop -WhatIf:$WhatIf
    } catch {
      Write-Host ("`t" + $_.Exception.Message)
    }
  }
}
```

To use this function, copy and paste the code into your PowerShell session. The following example
shows how to run the function to remove an older version of Azure PowerShell.

```powershell-interactive
Uninstall-AllModules -TargetModule Az -Version 0.7.0 -Force
```

As the script runs, it will display the name and version of each submodule that is being
uninstalled. To run the script to only see what would be deleted, without removing it,
use the `-WhatIf` option.

```output
Creating list of dependencies...
Uninstalling Az.Profile version 0.7.0
Uninstalling Az.Aks version 0.7.0
Uninstalling Az.AnalysisServices version 0.7.0
...
```

Run this command for every version of Azure PowerShell that you want to uninstall. For convenience, the following
script will uninstall all versions of Az __except__ for the latest.

```powershell-interactive
$versions = (Get-InstalledModule Az -AllVersions | Select-Object Version)
$versions[1..($versions.Length-1)]  | foreach { Uninstall-AllModules -TargetModule Az -Version ($_.Version) -Force }
```

## Uninstall the AzureRM module

If you have the Az module installed on your system and would like to uninstall AzureRM, there are two simple options that
don't require running the `Uninstall-AllModules` script above. Which method you follow depends on how you installed AzureRM.
If you're not sure, check the steps for uninstalling an MSI first.

### Uninstall MSI

If you installed the Azure PowerShell AzureRM modules using the MSI package, you must uninstall through the Windows
system rather than PowerShell.

| Platform | Instructions |
|----------|--------------|
| Windows 10 | Start > Settings > Apps |
| Windows 7 </br>Windows 8 | Start > Control Panel > Programs > Uninstall a program |

Once on this screen you should see "Azure PowerShell" in the program listing, and can uninstall from there.

### Uninstall from PowerShell

If you installed AzureRM from PowerShellGet, then you can remove the modules with the new `Uninstall-AzureRM` command. This removes _all_ AzureRM modules from your machine, but requires administrator privileges.

```powershell-interactive
Uninstall-AzureRm
```

If you can't successfully run the `Uninstall-AzureRM` command, use the `Uninstall-AllModules` script provided in this article instead.