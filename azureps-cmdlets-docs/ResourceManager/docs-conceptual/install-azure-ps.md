---
title: Install and configure the Azure PowerShell Service Management module | Microsoft Docs
description: How to install and configure Azure PowerShell for first time use.
services: azure
author: sdwheeler
manager: carmonm
ms.assetid: DF332CD7-E3E5-4CC1-8C01-380B2065193C
ms.product: azure
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.date: 03/06/2017
---

# Installing the Azure PowerShell Service Management module

The Azure Service Management module reference provides information about cmdlets that help you to
automate your Azure service management tasks. This reference includes information about the Azure
PowerShell modules, including system requirements, download links, and configurations tasks. It
also includes cmdlet help for the cmdlets and functions in the Azure PowerShell modules.

## To install the cmdlets

Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is
the preferred method of installation.

Installing items from the PowerShell Gallery requires the PowerShellGet module. Make sure you have
the appropriate version of PowerShellGet and other system requirements.

### How to get PowerShellGet

|OS Version|Install instructions|
|---|---|
|I have Windows 10 or Windows Server 2016|Built into Windows Management Framework (WMF) 5.0 included in the OS|
|I want to upgrade to PowerShell 5 on Windows 7, Windows 8, Windows 8.1, Windows Server 2008 R2 SP1, Windows Server 2012, or Windows Server 2012 R2|[Upgrade PowerShell by installing the WMF 5.0](http://go.microsoft.com/fwlink/?LinkId=398175)|
|I am running on a version of Windows with PowerShell 3 or PowerShell 4|[Download and install the PackageManagement module](http://go.microsoft.com/fwlink/?LinkID=746217)|

Other requirements

- PowerShell 3.0 or newer
- .NET Framework 4.5 or above
- The [NuGet provider](http://www.nuget.org) to work with the PowerShell Gallery

Run the following command from the Windows PowerShell console running as Administrator:

```powershell
Install-Module Azure
```

This command installs the latest Azure PowerShell Service Management module from PowerShell
Gallery. The Azure Service Management module shares dependencies with the Azure PowerShell Resource
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
module. To find the version of your module, type: `(Get-Module Azure).Version`.

For sample scripts that can help you automate some of the common tasks in Azure, see the
[Windows Azure Script Center](http://www.windowsazure.com/documentation/scripts/).

For general information about installing, learning, using, and customizing Windows PowerShell, see
[Scripting with Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).
