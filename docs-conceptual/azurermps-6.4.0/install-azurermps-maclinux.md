---
title: Install Azure PowerShell on macOS or Linux
description: How to install Azure PowerShell on macOS or Linux.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/06/2018
---
# Install Azure PowerShell on macOS or Linux

For non-Windows platforms, it's possible to run Azure PowerShell in PowerShell Core v6. This version of PowerShell
is built for use on any platform that supports .NET Core. To work with these platforms, there's a special .NET Core
version of Azure PowerShell available.

> [!NOTE]
> At this time, both PowerShell Core v6 and Azure PowerShell for .NET Core are still in beta.
> Support for these products is limited. If you have problems or discover bugs, please file an issue
> on GitHub.
>
> * [Issues for PowerShell Core v6](https://github.com/PowerShell/PowerShell/issues)
> * [Issues for Azure PowerShell](https://github.com/azure/azure-docs-powershell/issues)

## Install PowerShell Core

The installation instructions for PowerShell Core are different for macOS and most Linux distributions.
Detailed instructions can be found in the following articles:

* [Install PowerShell Core on macOS](/powershell/scripting/setup/installing-powershell-core-on-macos)
* [Install PowerShell Core on Linux](/powershell/scripting/setup/installing-powershell-core-on-linux)

## Install Azure PowerShell for .NET Core

PowerShell Core comes with the PowerShellGet module already installed. Installation of modules in PowerShell requires
elevated privileges, so you'll need to start your session as superuser:

```bash
sudo pwsh
```

To install Azure PowerShell, run the following command:

```powershell
Install-Module AzureRM.NetCore
```

> [!IMPORTANT]
> The `AzureRM` module detailed in other articles is not built for .NET Core and will not work with
> PowerShell Core. Both `AzureRM` and `AzureRM.NetCore` use the same cmdlet names, so the only difference is the
> name of the rollup module and which .NET version they are built against.

By default, the PowerShell gallery isn't configured as a trusted repository for PowerShellGet. The
first time you use the PSGallery you see the following prompt:

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the Set-PSRepository cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Answer `Yes` or `Yes to All` to continue with the installation.

## Sign in

To start working with Azure PowerShell, you need to load `AzureRM.Netcore` into your PowerShell session
with the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet, and then sign in
with your Azure credentials. Importing a module does __not__ require elevated privileges.

```powershell
# Import the module into the PowerShell session
Import-Module AzureRM.Netcore
# Connect to Azure with an interactive dialog for sign-in
Connect-AzureRmAccount
```

You'll need to repeat these steps for every new PowerShell session you start. Automatically importing the `AzureRM` module requires
setting up a PowerShell profile, which you can learn about in [About Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).
On macOS and Linux, you should work with your profile through the `$Profile` environment variable. To learn how to persist your Azure sign in across sessions, see [Persist user credentials across PowerShell sessions](context-persistence.md).

## Available cmdlets

The Azure PowerShell modules for .NET Core are still in development. These modules do not
provide the full set of cmdlets that are available for the Windows version of the modules. The
following functions are implemented in AzureRM.Netcore modules:

* Account management
  * Sign in with Microsoft account, Organizational account, or Service Principal through Microsoft
    Azure Active Directory
  * Save Credentials to disk with Save-AzureRmContext and load saved credentials using
    Import-AzureRmContext
* Environment
  * Get the different out-of-box Microsoft Azure environments
  * Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)
* Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.
  * Virtual Machine
  * App Service (Websites)
  * SQL Database
  * Storage
  * Network

## Next Steps

For more information about using Azure PowerShell, see the
[Get started with Azure PowerShell](get-started-azureps.md) article.
