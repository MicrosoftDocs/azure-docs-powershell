---
title: Uninstall Azure PowerShell
description: How to perform a complete uninstall of Azure PowerShell
ms.date: 09/11/2018
author: sptramer
ms.author: sttramer
ms.manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
---
# Uninstall the Azure PowerShell module

This article tells you how to uninstall an older version of Azure PowerShell, or completely remove it from
your system. If you've decided to completely uninstall the Azure PowerShell, give us some feedback
through the [Send-Feedback](/powershell/module/azurerm.profile/send-feedback) cmdlet.
If you encountered a bug, we'd appreciate it if you [file a GitHub issue](https://github.com/azure/azure-powershell/issues).

## Uninstall MSI

If you installed Azure PowerShell using the MSI package, you must uninstall through the Windows
system rather than PowerShell.

| Platform | Instructions |
|----------|--------------|
| Windows 10 | Start > Settings > Apps |
| Windows 7 </br>Windows 8 | Start > Control Panel > Programs > Uninstall a program |

Once on this screen you should see "Azure PowerShell" in the program listing, and can uninstall from there.

## Uninstall from PowerShell

If you installed Azure PowerShell using PowerShellGet, you can use the
[Uninstall-Module](/powershell/module/powershellget/uninstall-module) cmdlet. However,
`Uninstall-Module` only uninstalls one module. To remove Azure PowerShell completely, you must
uninstall each module individually. Uninstallation can be complicated if you have more than one version of Azure
PowerShell installed.

The following script queries the PowerShell Gallery to get a list of dependent submodules. Then, the script
uninstalls the correct version of each submodule.

```powershell
function Uninstall-AllModules {
  param(
    [Parameter(Mandatory=$true)]
    [string]$TargetModule,

    [Parameter(Mandatory=$true)]
    [string]$Version,

    [switch]$Force
  )

  $AllModules = @()

  'Creating list of dependencies...'
  $target = Find-Module $TargetModule -RequiredVersion $version
  $target.Dependencies | ForEach-Object {
    $AllModules += New-Object -TypeName psobject -Property @{name=$_.name; version=$_.requiredversion}
  }
  $AllModules += New-Object -TypeName psobject -Property @{name=$TargetModule; version=$Version}

  foreach ($module in $AllModules) {
    Write-Host ('Uninstalling {0} version {1}' -f $module.name,$module.version)
    try {
      Uninstall-Module -Name $module.name -RequiredVersion $module.version -Force:$Force -ErrorAction Stop
    } catch {
      Write-Host ("`t" + $_.Exception.Message)
    }
  }
}
```

To use this function, copy and paste the code into your PowerShell session. The following example
shows how to run the function to remove an older version of Azure PowerShell.

```powershell
Uninstall-AllModules -TargetModule AzureRM -Version 4.4.1 -Force
```

As the script runs, it will display the name and version of each submodule that is being
uninstalled.

```output
Creating list of dependencies...
Uninstalling AzureRM.Profile version 3.4.1
Uninstalling Azure.Storage version 3.4.1
Uninstalling AzureRM.AnalysisServices version 0.4.7
Uninstalling Azure.AnalysisServices version 0.4.7
...
```

Run this command for every version of Azure PowerShell that you want to uninstall.
