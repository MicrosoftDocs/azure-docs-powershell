---
title: Install and configure the Azure PowerShell Service Management module | Microsoft Docs
description: How to install and configure Azure PowerShell for first time use.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/06/2017
ms.custom: devx-track-azurepowershell
---

# Installing the Azure PowerShell Service Management module

Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is
the preferred method of installation.

## Step 1: Install PowerShellGet

Installing items from the PowerShell Gallery requires the PowerShellGet module. Make sure you have
the appropriate version of PowerShellGet and other system requirements. Run the following command
to see if you have PowerShellGet installed on your system.

```powershell
Get-InstalledModule PowerShellGet -AllVersions | Select-Object Name,Version,Path
```

You should see something similar to the following output:

```output
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

If you do not have PowerShellGet installed, see the
[How to get PowerShellGet](#how-to-get-powershellget).

## Step 2: Install Azure PowerShell

Run the following command from the Windows PowerShell console running as Administrator:

```powershell
Install-Module Azure
```

The Azure module is a rollup module for the Azure Resource Manager cmdlets. When you install the
AzureRM module, any other Azure modules that have not previously been installed will be
downloaded and installed from the PowerShell Gallery.

The Azure Service Management module shares dependencies with the Azure PowerShell Resource
Manager modules. If you have installed the Azure PowerShell Resource Manager modules, you will need
to add the `-AllowClobber` parameter to the install command. This allows this existing shared
dependencies to be updated. Without this parameter, installation of the module fails.

```powershell
Install-Module Azure -AllowClobber
```

After you install this module, you can import the module by running the following command:

```powershell
Import-Module Azure
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

Azure PowerShell modules are updated frequently. If you notice that the online cmdlet help includes
cmdlets or parameters that are not in your module, download and install the latest version of the
module. To find the version of your module, type: `(Get-InstalledModule Azure).Version`.

For sample scripts that can help you automate some of the common tasks in Azure, see the
[Windows Azure Script Center](https://www.windowsazure.com/documentation/scripts/).

For general information about installing, learning, using, and customizing Windows PowerShell, see
[Scripting with Windows PowerShell](/powershell/scripting/learn/ps101/00-introduction).

### How to get PowerShellGet

|OS Version|Install instructions|
|---|---|
|I have Windows 10 or Windows Server 2016|Built into Windows Management Framework (WMF) 5.0 included in the OS|
|I want to upgrade to PowerShell 5|[Install the latest version of WMF](https://www.microsoft.com/download/details.aspx?id=54616)|

<div id="helpmechoose"/>

### Checking the version of Azure PowerShell

Although we encourage you to upgrade to the latest version as early as possible, several versions
of Azure PowerShell are support. To determine the version of Azure PowerShell you have installed,
run `Get-InstalledModule Azure` from your command line.

```powershell
Get-InstalledModule Azure -AllVersions | Select-Object Name,Version,Path
```
