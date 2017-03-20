---
title: Install and configure Azure PowerShell | Microsoft Docs
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

# Install and configure Azure PowerShell

Azure PowerShell is a set of modules that provide cmdlets to manage Azure with Windows PowerShell.
You can use the cmdlets to create, test, deploy, and manage solutions and services delivered through
the Azure platform. In most cases, the cmdlets can be used for the same tasks as the Azure Portal,
such as creating and configuring cloud services, virtual machines, virtual networks, and web apps.

## Step 1: Install PowerShellGet

Installing Azure PowerShell from the [PowerShell Gallery](https://www.powershellgallery.com/) is
the preferred method of installation. For alternative methods of installation, see the
[Other installation methods](#other-installation-methods) section of this document.

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

The AzureRM module is a rollup module for the Azure Resource Manager cmdlets. The definition of the
AzureRM module includes a list all of the dependent AzureRM service modules and their versions.
This list assures that the proper version of each module is installed for the specified version of
the rollup module. When you install the AzureRM module, any Azure Resource Manager module that has
not previously been installed will be downloaded and installed from the PowerShell Gallery.

Once the module is installed, you need to load the module into your PowerShell session. Modules are
loaded using the `Import-Module` cmdlet, as follows:

```powershell
Import-Module AzureRM
```

## Step 3: Connect to an Azure account

You can run the cmdlets from the standard Windows PowerShell console, or from PowerShell Integrated
Scripting Environment (ISE). The cmdlets need your subscription information so they can manage your
services.

Sign on interactively:

1. Type `Login-AzureRmAccount`

2. Type the email address and password associated with your account. Azure authenticates and saves
   the credential information, and then closes the window.

Now you are signed into Azure. You can use Azure PowerShell to create and manage resources in
resources in your account.

## <a id="Help"></a>Getting help

These resources provide help for specific cmdlets:

* Release notes for migrating to a newer release can be found at:
  [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).
* For help from the community, try these popular forums:
    + [Azure forum on MSDN](http://go.microsoft.com/fwlink/p/?LinkId=320212)
    + [stackoverflow](http://go.microsoft.com/fwlink/?LinkId=320213)

## Other installation methods

Azure PowerShell has multiple installation methods. Using PowerShellGet with the PowerShell Gallery
is the preferred method. Azure PowerShell can be installed using the Web Platform Installer (WebPI)
or by using the MSI file available from
[GitHub](https://github.com/Azure/azure-powershell/releases/latest).

### Install using the Web Platform Installer

Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.
Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.

> [!NOTE]
> If you have previously installed Azure modules from the PowerShell Gallery, the installer
> will automatically remove them. This simplifies your environment by ensuring that only one version
> of Azure PowerShell is installed. However, there are scenarios where you may need multiple
> versions installed at the same time.
>
> PowerShell Gallery modules installs modules in
> `$env:ProgramFiles\WindowsPowerShell\Modules`. In contrast, the WebPI installer will
> install the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.
>
> If an error occurs during install, you can manually remove the Azure* folders in your
> `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.

Once the installation completes, your `$env:PSModulePath` setting should include the directories
containing the Azure PowerShell cmdlets. The following command can be used to verify that the Azure
PowerShell is installed properly.

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure* | Select-Object Name, Version, Path
```

> [!NOTE]
> There is a known issue that can occur when installing from WebPI. If your computer requires a
restart due to system updates or other installations, it may cause updates to `$env:PSModulePath` to
fail to include the path where Azure PowerShell is installed.

When attempting to load or execute cmdlets after installation, you can receive the following error
message:

```
PS C:\> Login-AzureRmAccount
Login-AzureRmAccount : The term 'Login-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Login-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Login-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

This can be corrected by restarting the machine or importing the module using the fully-qualified
path. For example:

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

### Install using the MSI Package

Azure PowerShell can be installed using the MSI file available from
[GitHub](https://github.com/Azure/azure-powershell/releases/latest). If you have installed previous
versions of Azure modules the installer will automatically remove them. The MSI package installs
modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version specific
folders.

## Installing module versions side-by-side

Version 2.1.0 and version 1.2.6 are the first module versions designed to be installed and used
side-by-side. You should always install the latest available version of Azure PowerShell. But if
you have scripts written using an earlier version, you should check for breaking changes in the
newer version.

If you are using Azure Stack you will need to install Azure PowerShell v1.2.8. For complete
instructions on using Azure PowerShell with Azure Stack see [Install PowerShell for Azure
Stack](/azure/azure-stack/azure-stack-powershell-install).

The PowerShellGet method of installation is the only method that supports the installation of
multiple versions. The following commands illustrate how to install multiple versions of Azure
PowerShell:

```powershell
Install-Module -Name AzureRM -RequiredVersion 3.6.0
Install-Module -Name AzureRM -RequiredVersion 1.2.8
Install-Module -Name AzureStack
```

Only one version of the module can be loaded in a PowerShell session. You must open a new
PowerShell window and use `Import-Module` to import a specific version of the AzureRM cmdlets:

```powershell
Import-Module AzureRM -RequiredVersion 1.2.8
Import-Module AzureStack
```

> [!NOTE]
> Versions prior to v2.1.0 (other than v1.2.6) do not work well side-by-side with other Azure
PowerShell module versions. When loading an earlier version of the Azure PowerShell modules using a
command like the one above, incompatible versions of the **AzureRM.Profile** module will be loaded,
resulting in the cmdlets asking you to log in whenever you execute a cmdlet, even after you have
logged in.

### Updating to a new version of Azure PowerShell

PowerShellGet has the ability to update an installed module when a new version has been released to
the PowerShell Gallery. Using the `Update-Module` cmdlet, you can download and install the latest
version. By default, the new version will be installed side-by-side with any other versions that
have been installed. If you want to update the current version, you must use the `-Force`
parameter. For example:

```powershell
Update-Module -Name AzureRM -Force
```

> [!NOTE]
> The Azure and AzureRM modules share common dependencies. So if you use both modules you should
update both.

## Next Steps

For more information about using Azure PowerShell, see the following articles:

* [Sign on with Azure PowerShell](authenticate-azureps.md)
* [Get started with Azure PowerShell](get-started-azureps.md)
* [Manage Azure subscriptions with Azure PowerShell](manage-subscriptions-azureps.md)
* [Create service principals in Azure using Azure PowerShell](create-azure-service-principal-azureps.md)

## Learn More

See the following resources to learn more about using the cmdlets:

* For basic instructions about using Windows PowerShell, see
  [Using Windows PowerShell](https://msdn.microsoft.com/powershell/scripting/getting-started/fundamental/using-windows-powershell).
* For sample scripts and instructions to help you learn to use scripting to manage Azure, see the
  [Script Center](https://gallery.technet.microsoft.com/scriptcenter/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=WindowsAzure&f%5B0%5D.Text=Windows%20Azure).