---
description: How to perform a complete uninstall of Azure PowerShell
ms.custom: devx-track-azurepowershell
ms.date: 08/01/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Uninstall Azure PowerShell
---

# How to uninstall Azure PowerShell modules

This article explains how to uninstall Azure PowerShell, or completely remove it from your system.
If you've decided to completely uninstall Azure PowerShell and don't plan to reinstall it, give us
some feedback through the [Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet. If
you encountered a bug, [file a GitHub issue](https://github.com/azure/azure-powershell/issues).

## Uninstall the Az module

If you have the Az module installed on your system and would like to uninstall it, there are
two options. Which method you follow depends on how you installed the Az module. If you're not
sure of your original installation method, follow the MSI steps for uninstalling first.

### Option 1: Uninstall the Az PowerShell module from MSI

If you installed Az PowerShell module using the MSI package, you must uninstall through the Windows
system rather than PowerShell.

|         Platform         |                      Instructions                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Start > Settings > Apps                                |
| Windows 7 </br>Windows 8 | Start > Control Panel > Programs > Uninstall a program |

Once on this screen, you should see **Azure PowerShell** in the program listing. This is the app to
uninstall. If you don't see this program listed, then you installed through PowerShellGet and
should follow the instructions outlined in option 2.

### Option 2: Uninstall the Az PowerShell module from PowerShellGet

When the Az PowerShell module is installed, it installs numerous PowerShell modules for different
Azure services. All the modules begin with an Az prefix.

> [!IMPORTANT]
> Run PowerShell elevated as an admin if any version of the Az PowerShell module is installed in the
> all users `$env:PSModulePath`.

To uninstall the Az PowerShell module, you can use the
[Uninstall-Module](/powershell/module/powershellget/uninstall-module) cmdlet. However,
`Uninstall-Module` only uninstalls the modules specified for the **Name** parameter. To remove the Az
PowerShell module completely, you must uninstall each module individually.

> [!NOTE]
> Uninstallation can be complicated if you have more than one version of the Az PowerShell module
> installed. Because of this complexity, we only support uninstalling all versions of the Az
> PowerShell module that are installed.

First, you'll need a list of all the Az PowerShell module versions installed on your system.

```powershell
Get-InstalledModule -Name Az -AllVersions -OutVariable AzVersions
```

You can use the following example to generate a list of all the Az PowerShell modules that need to
be uninstalled in addition to the Az module.

```powershell
($AzVersions |
  ForEach-Object {
    Import-Clixml -Path (Join-Path -Path $_.InstalledLocation -ChildPath PSGetModuleInfo.xml)
  }).Dependencies.Name | Sort-Object -Descending -Unique -OutVariable AzModules
```

Remove the Az modules from memory and then uninstall them.

```powershell
$AzModules |
  ForEach-Object {
    Remove-Module -Name $_ -ErrorAction SilentlyContinue
    Write-Output "Attempting to uninstall module: $_"
    Uninstall-Module -Name $_ -AllVersions
  }
```

The final step is to remove the Az PowerShell module.

```powershell
Remove-Module -Name Az -ErrorAction SilentlyContinue
Uninstall-Module -Name Az -AllVersions
```

## Uninstall the AzureRM module

If you have the Az module installed on your system and would like to uninstall AzureRM, there are
two options. Which method you follow depends on how you installed the AzureRM module. If you're not
sure of your original installation method, follow the MSI steps for uninstalling first.

### Option 1: Uninstall the AzureRM PowerShell module from MSI

If you installed the AzureRM PowerShell module using the MSI package, you must uninstall through the
Windows system rather than PowerShell.

|         Platform         |                      Instructions                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Start > Settings > Apps                                |
| Windows 7 </br>Windows 8 | Start > Control Panel > Programs > Uninstall a program |

Once on this screen, you should see **Azure PowerShell** or **Microsoft Azure PowerShell - Month
Year** in the program listing. This is the app to uninstall. If you don't see this program listed,
then you installed through PowerShellGet, and should follow the next set of instructions.

### Option 2: Uninstall the AzureRM PowerShell module from PowerShellGet

If you installed AzureRM with PowerShellGet, then you can remove the modules with the
[Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm) cmdlet, available as part of
the `Az.Accounts` module.

To use `Uninstall-AzureRM` from the `Az.Accounts` module, you need to have the Az PowerShell module
installed. Having both the AzureRM and the Az modules installed at the same time isn't supported,
however the Az module can be used to immediately uninstall the AzureRM module. You can install the
Az module and bypass the AzureRM module warning with the following command if you don't have the Az
module installed already:

```powershell
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```

Once the Az module is installed, the following command removes _all_ AzureRM modules from your machine. It
requires administrator privileges.

```powershell
Uninstall-AzureRm
```
