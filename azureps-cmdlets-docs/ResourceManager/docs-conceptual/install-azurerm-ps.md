---
title: Install and configure Azure PowerShell | Microsoft Docs
description: How to install and configure Azure PowerShell for first time use.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-resource-manager
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/30/2017
---

# Install and configure Azure PowerShell

Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is
the preferred method of installation.

## Step 1: Install PowerShellGet

Installing items from the PowerShell Gallery requires the PowerShellGet module. Make sure you have
the appropriate version of PowerShellGet and other system requirements. Run the following command
to see if you have PowerShellGet installed on your system.

```powershell
Get-Module PowerShellGet -list | Select-Object Name,Version,Path
```

You should see something similar to the following output:

```
Name          Version Path
----          ------- ----
PowerShellGet 1.0.0.1 C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1
```

If you do not have PowerShellGet installed, see the [How to get PowerShellGet](#how-to-get-powershellget)
section of this article.

> [!NOTE] > Using PowerShellGet requires an Execution Policy that allows you to run scripts. For
> more information about PowerShell's Execution Policy, see
> [About Execution Policies](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/about/about_execution_policies).

## Step 2: Install Azure PowerShell

Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges. Run the
following command from an elevated PowerShell session:

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM
```

> [!NOTE]
> If you have a version older than 2.8.5.201 of NuGet, you will be prompted to download and install
the latest version of NuGet.

The AzureRM module is a rollup module for the Azure Resource Manager cmdlets. When you install the
AzureRM module, any Azure Resource Manager module that has not previously been installed will be
downloaded and installed from the PowerShell Gallery.

Once the module is installed, you need to load the module into your PowerShell session. Modules are
loaded using the `Import-Module` cmdlet, as follows:

```powershell
Import-Module AzureRM
```

## Next Steps

For more information about using Azure PowerShell, see the following articles:

* [Get started with Azure PowerShell](get-started-azureps.md)

## Frequently asked questions

### How to get PowerShellGet

|OS Version|Install instructions|
|---|---|
|I have Windows 10 or Windows Server 2016|Built into Windows Management Framework (WMF) 5.0 included in the OS|
|I want to upgrade to PowerShell 5|[Install the latest version of WMF](http://go.microsoft.com/fwlink/?LinkId=398175)|
|I am running on a version of Windows with PowerShell 3 or PowerShell 4|[Get the PackageManagement modules](http://go.microsoft.com/fwlink/?LinkID=746217)|

<a id="helpmechoose"></a>
### Checking the version of Azure PowerShell

Although we encourage you to upgrade to the latest version as early as possible, several versions of Azure PowerShell are support.  To determine the version of Azure PowerShell you have installed, run `Get-Module AzureRM` from your command line.

```powershell
Get-Module AzureRM
```


### Updating to a new version of Azure PowerShell

PowerShellGet has the ability to update an installed module when a new version has been released to
the PowerShell Gallery. Using the `Update-Module` cmdlet, you can download and install the latest
version. The new version will be installed side-by-side with any other versions that
have been installed. The `Update-Module` cmdlet does not remove previous versions.

If you want to reinstall the current version, you must use the `-Force` parameter. For example:

```powershell
Update-Module -Name AzureRM -Force
```

> [!NOTE]
> If you have deployments that use the classic deployment model that cannot be converted you can
install the Service Management version of Azure PowerShell. For more information, see
[Install the Azure PowerShell Service Management module](overview?view=azuresmps-3.7.0).
The Azure and AzureRM modules share common dependencies. So if you use both modules you should
update both.


### Installing module versions side-by-side

The PowerShellGet method of installation is the only method that supports the installation of
multiple versions. For example, you may have scripts written using a previous version of Azure
PowerShell that you don't have the time or resources to updated. The following commands illustrate
how to install multiple versions of Azure PowerShell:

```powershell
Install-Module -Name AzureRM -RequiredVersion 3.7.0
Install-Module -Name AzureRM -RequiredVersion 1.2.9
```

Only one version of the module can be loaded in a PowerShell session. You must open a new
PowerShell window and use `Import-Module` to import a specific version of the AzureRM cmdlets:

```powershell
Import-Module AzureRM -RequiredVersion 1.2.9
```

> [!NOTE]
> Version 2.1.0 and version 1.2.6 are the first module versions designed to be installed and used
side-by-side. When loading an earlier version of the Azure PowerShell modules using a
command like the one above, incompatible versions of the **AzureRM.Profile** module will be loaded,
resulting in the cmdlets asking you to log in whenever you execute a cmdlet, even after you have
logged in.

### Other installation methods

For information about installing using the Web Platform Installer or the MSI Package, see
[Other installation methods](other-install.md)
