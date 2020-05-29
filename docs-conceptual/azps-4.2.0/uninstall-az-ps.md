---
title: Uninstall Azure PowerShell
description: How to perform a complete uninstall of Azure PowerShell
ms.date: 10/22/2019
ms.devlang: powershell
ms.topic: conceptual
---
# Uninstall the Azure PowerShell module

This article tells you how to uninstall an older version of Azure PowerShell, or completely remove it from
your system. If you've decided to completely uninstall the Azure PowerShell, give us some feedback
through the [Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet.
If you encountered a bug, we'd appreciate it if you [file a GitHub issue](https://github.com/azure/azure-powershell/issues) so that it can be fixed.

## Uninstall Azure PowerShell from MSI

If you installed Azure PowerShell using the MSI package, you must uninstall through the Windows system rather than PowerShell.

| Platform | Instructions |
|----------|--------------|
| Windows 10 | Start > Settings > Apps |
| Windows 7 </br>Windows 8 | Start > Control Panel > Programs > Uninstall a program |

Once on this screen you should see __Azure PowerShell__ in the program listing. This is the app to uninstall. If you don't see this program listed, then
you installed through PowerShellGet, and should follow the next set of instructions.

## Uninstall Azure PowerShell from PowerShell Get

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

<a name="uninstall-script"/>

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
    if ($_.PSObject.Properties.Name -contains 'requiredVersion') {
      $AllModules += New-Object -TypeName psobject -Property @{name=$_.name; version=$_.requiredVersion}
    }
    else { # Assume minimum version
      # Minimum version actually reports the installed dependency
      # which is used, not the actual "minimum dependency." Check to
      # see if the requested version was installed as a dependency earlier.
      $candidate = Get-InstalledModule $_.name -RequiredVersion $version -ErrorAction Ignore
      if ($candidate) {
        $AllModules += New-Object -TypeName psobject -Property @{name=$_.name; version=$version}
      }
      else {
        $availableModules = Get-InstalledModule $_.name -AllVersions
        Write-Warning ("Could not find uninstall candidate for {0}:{1} - module may require manual uninstall. Available versions are: {2}" -f $_.name,$version,($availableModules.Version -join ', '))
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

> [!NOTE]
> If this script can't match an exact dependency with the same version to uninstall, it won't uninstall _any_ version of that dependecy. This is because there may be
> other versions of the target module on your system which rely on these dependencies. In this case, the available versions of the dependency are listed.
> You can then remove any old versions manually with `Uninstall-Module`.

Run this command for every version of Azure PowerShell that you want to uninstall. For convenience, the following
script will uninstall all versions of Az __except__ for the latest.

```powershell-interactive
$versions = (Get-InstalledModule Az -AllVersions | Select-Object Version)
$versions[0..($versions.Length-2)]  | foreach { Uninstall-AllModules -TargetModule Az -Version ($_.Version) -Force }
```

## Uninstall the AzureRM module

If you have the Az module installed on your system and would like to uninstall AzureRM, there are two options that
don't require running the `Uninstall-AllModules` script above. Which method you follow depends on how you installed the AzureRM module.
If you're not sure of your original install method, follow the steps for uninstalling an MSI first.

### Uninstall Azure PowerShell MSI

If you installed the Azure PowerShell AzureRM modules using the MSI package, you must uninstall through the Windows
system rather than PowerShell.

| Platform | Instructions |
|----------|--------------|
| Windows 10 | Start > Settings > Apps |
| Windows 7 </br>Windows 8 | Start > Control Panel > Programs > Uninstall a program |

Once on this screen you should see __Azure PowerShell__ or __Microsoft Azure PowerShell - Month Year__ in the program listing. This is the app to uninstall. If you don't see this program listed, then
you installed through PowerShellGet, and should follow the next set of instructions.

### Uninstall from PowerShell

If you installed AzureRM with PowerShellGet, then you can remove the modules with the [Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm) command, available as
part of the `Az.Accounts` module. This removes _all_ AzureRM modules from your machine, but requires administrator privileges.

```powershell-interactive
Uninstall-AzureRm
```
or
```powershell-interactive
Uninstall-Module AzureRm
```

If you can't successfully run the `Uninstall-AzureRM` command, use the [`Uninstall-AllModules` script](#uninstall-script) provided in this article with the following invocation:

```powershell-interactive
$versions = (Get-InstalledModule AzureRM -AllVersions | Select-Object Version)
$versions | foreach { Uninstall-AllModules -TargetModule AzureRM -Version ($_.Version) -Force }
```
or
```powershell-interactive
foreach ($module in (Get-Module -ListAvailable AzureRM*).Name |Get-Unique) {
   write-host "Removing Module $module"
   Uninstall-module $module
}
```
