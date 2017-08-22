---
title: Install and configure Azure PowerShell | Microsoft Docs
description: How to install and configure Azure PowerShell for first time use.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/17/2017
---

# Install and configure Azure PowerShell

Installing Azure PowerShell from the PowerShell Gallery is the preferred method of installation.

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

> [!NOTE]
> Using PowerShellGet requires an Execution Policy that allows you to run scripts. For more
> information about PowerShell's Execution Policy, see
> [About Execution Policies](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/about/about_execution_policies).

## Step 2: Install Azure PowerShell

Installing Azure PowerShell from the PowerShell Gallery requires elevated privileges. Run the
following command from an elevated PowerShell session:

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM
```

By default, the PowerShell gallery is not configured as a Trusted repository for PowerShellGet. The
first time you use the PSGallery you see the following prompt:

```
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
```

Answer 'Yes' or 'Yes to All' to continue with the installation.

> [!NOTE]
> If you have a version older than 2.8.5.201 of NuGet, you are prompted to download and install
> the latest version of NuGet.

The AzureRM module is a rollup module for the Azure Resource Manager cmdlets. When you install the
AzureRM module, any Azure PowerShell module not previously installed is downloaded and from the
PowerShell Gallery.

If you have a previous version of Azure PowerShell installed you may receive an error. To resolve
this issue, see the [Updating to a new version of Azure PowerShell](#update-azps) section of this
article.

## Step 3: Load the AzureRM module
Once the module is installed, you need to load the module into your PowerShell session. You should
do this in a normal (non-elevated) PowerShell session. Modules are loaded using the `Import-Module`
cmdlet, as follows:

```powershell
Import-Module AzureRM
```

## Next Steps

For more information about using Azure PowerShell, see the following articles:

* [Get started with Azure PowerShell](get-started-azureps.md)

## Reporting issues and feedback

If you encounter any bugs with the tool, file an issue in the
[Issues](https://github.com/Azure/azure-powershell/issues) section of our GitHub repo. To provide
feedback from the command line, use the `Send-Feedback` cmdlet.

## Frequently asked questions

### How to get PowerShellGet

|OS Version|Install instructions|
|---|---|
|I have Windows 10 or Windows Server 2016|Built into Windows Management Framework (WMF) 5.0 included in the OS|
|I want to upgrade to PowerShell 5|[Install the latest version of WMF](https://www.microsoft.com/en-us/download/details.aspx?id=54616)|
|I am running on a version of Windows with PowerShell 3 or PowerShell 4|[Get the PackageManagement modules](http://go.microsoft.com/fwlink/?LinkID=746217)|

<a id="helpmechoose"></a>
### Checking the version of Azure PowerShell

Although we encourage you to upgrade to the latest version as early as possible, several versions
of Azure PowerShell are supported. To determine the version of Azure PowerShell you have installed,
run `Get-Module AzureRM` from your command line.

```powershell
Get-Module AzureRM -list | Select-Object Name,Version,Path
```

### Support for classic deployment methods

If you have deployments that use the classic deployment model you can install the Service
Management version of Azure PowerShell. For more information, see [Install the Azure PowerShell
Service Management module](/powershell/azure/servicemanagement/install-azure-ps). The Azure and AzureRM modules share
common dependencies. If you use both the Azure and AzureRM modules, you should install the same
version of each package.

### <a id="update-azps"></a>Updating to a new version of Azure PowerShell

If you have a previous version of Azure PowerShell installed that includes the Service Management
module, you may receive the following error:

```
PackageManagement\Install-Package : A command with name 'Get-AzureStorageContainerAcl' is already
available on this system. This module 'Azure.Storage' may override the existing commands. If you
still want to install this module 'Azure.Storage', use -AllowClobber parameter.

At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PSModule.psm1:1772 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], Exception
    + FullyQualifiedErrorId : CommandAlreadyAvailable,Validate-ModuleCommandAlreadyAvailable,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage
```

As the error message states, you need to use the -AllowClobber parameter to install the module. Use
the following command:

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM -AllowClobber
```

For more information, see the help topic for
[Install-Module](https://msdn.microsoft.com/powershell/reference/5.1/PowerShellGet/install-module).

### Installing module versions side by side

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
side by side. When loading an earlier version of the Azure PowerShell, incompatible versions of the
**AzureRM.Profile** module are loaded. This results in the cmdlets prompting you to log in whenever
you execute a cmdlet.

### Other installation methods

For information about installing using the Web Platform Installer or the MSI Package, see
[Other installation methods](other-install.md)
