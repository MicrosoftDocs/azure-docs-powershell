---
title: Install and configure the Azure PowerShell Service Management module | Microsoft Docs
description: How to install and configure Azure PowerShell for first time use.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
---

# Installing the Azure PowerShell Service Management module

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is
the preferred method of installation.

## Step 1: Install PowerShellGet

Installing items from the PowerShell Gallery requires the PowerShellGet module. Make sure you have
the appropriate version of PowerShellGet and other system requirements. Run the following command
to see if you have PowerShellGet installed on your system.

```powershell
Get-InstalledModule PowerShellGet -AllVersions |
  Select-Object -Property Name, Version, Path
```

You should see something similar to the following output:

```Output
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

If you do not have PowerShellGet installed, see the
[How to get PowerShellGet](#how-to-get-powershellget).

## Step 2: Install Azure PowerShell

Run the following command from the Windows PowerShell console running as Administrator:

```powershell
Install-Module -Name Azure
```

The Azure module is a rollup module for the Azure Service Management cmdlets. When you install the
AzureRM module, any other Azure modules that have not previously been installed will be downloaded
and installed from the PowerShell Gallery.

The Azure Service Management module shares dependencies with the Azure PowerShell Resource Manager
modules. If you have installed the Azure PowerShell Resource Manager modules, you will need to add
the `AllowClobber` parameter to the install command. This allows the existing shared dependencies to
be updated. Without this parameter, installation of the module fails.

```powershell
Install-Module -Name Azure -AllowClobber
```

After you install this module, you can import the module by running the following command:

```powershell
Import-Module -Name Azure
```

## To use the cmdlets

To start working with the Azure Service Management cmdlets, first log on to your Azure account. To
log on to your account, run the following command:

```powershell
Add-AzureAccount
```

After logging into Azure, Azure PowerShell creates a context for the given session. That context
contains the Azure PowerShell environment, account, tenant, and subscription that will be used for
all cmdlets within that session. Now you are ready to use the modules below.

## Azure Service Management cmdlets

If you notice that the online cmdlet help includes cmdlets or parameters that are not in your
module, download and install the latest version of the module.

For sample scripts that can help you automate some of the common tasks in Azure, see the
[Windows Azure Script Center](https://www.windowsazure.com/documentation/scripts/).

For general information about installing, learning, using, and customizing Windows PowerShell, see
[Scripting with Windows PowerShell](/powershell/scripting/learn/ps101/00-introduction).

### How to get PowerShellGet

|                    OS Version                     |                                     Install instructions                                      |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| I have Windows 10, Windows Server 2016, or higher | Built into Windows Management Framework (WMF) 5.x included in the OS                          |
| I want to upgrade to PowerShell 5                 | [Install the latest version of WMF](https://www.microsoft.com/download/details.aspx?id=54616) |

### Checking the version of Azure PowerShell

To determine the version of Azure PowerShell you have installed, run
`Get-InstalledModule -Name Azure` from PowerShell.

```powershell
Get-InstalledModule -Name Azure -AllVersions |
  Select-Object -Property Name,Version,Path
```
