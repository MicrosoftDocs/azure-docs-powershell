---
title: Other ways to install Azure PowerShell
description: How to install Azure PowerShell using the MSI package or the Web Platform Installer.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/06/2018
---

# Other installation methods

This article explains how to install Azure PowerShell using an MSI or Web Platform Installer (WebPI). You can also
run Azure PowerShell from inside of a Docker container. Use these installation methods only if they're necessary
for your system. The canonical way to install Azure PowerShell is through PowerShellGet. For instructions on using
PowerShellGet to install Azure PowerShell, see [Install Azure PowerShell with PowerShellGet](install-azurerm-ps.md).

To install on Linux or macOS environments, see [Install Azure PowerShell on macOS or Linux](install-azurermps-maclinux.md).

## Install or update on Windows using the Web Platform Installer

Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.
Download the [Azure PowerShell WebPI package](http://aka.ms/webpi-azps) and start the install.

> [!NOTE]
> If you have previously installed Azure modules from the PowerShell Gallery, the installer
> automatically removes them. This simplifies your environment by ensuring that only one version
> of Azure PowerShell is installed. However, there are scenarios where you may need multiple
> versions installed at the same time.
>
> PowerShell Gallery modules install modules in
> `$env:ProgramFiles\WindowsPowerShell\Modules`. In contrast, the WebPI installer
> installs the Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`.
>
> If an error occurs during install, you can manually remove the `Azure*` folders in your
> `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.

Once the installation completes, your `$env:PSModulePath` setting should include the directories
containing the Azure PowerShell cmdlets. The following command can be used to verify that the Azure
PowerShell is installed properly:

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
PS C:\> Connect-AzureRmAccount
Connect-AzureRmAccount : The term 'Connect-AzureRmAccount' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Connect-AzureRmAccount
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Connect-AzureRmAccount:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

This error can be corrected by restarting the machine or importing the module using the fully
qualified path.

```powershell
Import-Module "$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\AzureRM.psd1"
```

## Install or update on Windows using the MSI Package

Azure PowerShell can be installed using the MSI file available from
[GitHub](https://aka.ms/azps-release). If you have installed previous
versions of Azure modules, the installer automatically removes them. The MSI package installs
modules in `$env:ProgramFiles\WindowsPowerShell\Modules` but does not create version-specific
folders.

## Run in a Docker container

We maintain a set of Docker images preconfigured with Azure PowerShell. There are two types of containers available: Those running traditional
PowerShell on Windows, and a container running PowerShell Core on either Windows or Linux.

| Environment | Docker image |
|-------------|--------------|
| PowerShell on Windows | [azuresdk/azure-powershell](https://hub.docker.com/r/azuresdk/azure-powershell/) |
| PowerShell Core on Windows | [azuresdk/azure-powershell-core:nanoserver](https://hub.docker.com/r/azuresdk/azure-powershell-core/) |
| PowerShell Core on Linux | [azuresdk/azure-powershell-core:latest](https://hub.docker.com/r/azuresdk/azure-powershell-core/) |

To run any of these containers, you use `docker run -it $ImageName` to get an interactive terminal. For example, to run the PowerShell Core on Linux container,
use:

```powershell
docker run -it azuresdk/azure-powershell-core:latest
```

> [!NOTE]
> To run a Windows container in Docker, your host OS must be Windows and Docker must be set to
> run Windows containers. To learn about switching between Windows and Linux environments in Docker,
> see the Docker documentation [Switch between Windows and Linux containers](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).