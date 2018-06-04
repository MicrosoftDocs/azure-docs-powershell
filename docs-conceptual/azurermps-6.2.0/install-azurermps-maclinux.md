---
title: Install Azure PowerShell on macOS and Linux
description: How to install Azure PowerShell on macOS and Linux.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/06/2018
---
# Install Azure PowerShell on macOS and Linux

For non-Windows platforms, it's possible to run Azure PowerShell on top of PowerShell Core v6. Rather than
the standard Azure PowerShell built on .NET Framework for Windows, this product is built for .NET Core and can run on any
platform which supports the .Net Core runtime.

> [!NOTE]
> At this time, both PowerShell Core v6 and Azure PowerShell for .NET Core are still in beta.
> Support for these products is limited. If you have problems or discover bugs, please file an issue
> on GitHub.
>
> * [Issues for PowerShell Core v6](https://github.com/PowerShell/PowerShell/issues)
> * [Issues for Azure PowerShell](https://github.com/azure/azure-docs-powershell/issues)

## Install PowerShell Core v6

Installing PowerShell Core v6 on Linux or macOS varies depending on the Linux distribution and OS version.
Detailed instructions can be found in the following articles:

- [Installing PowerShell Core on macOS](/powershell/scripting/setup/installing-powershell-core-on-macos)
- [Installing PowerShell Core on Linux](/powershell/scripting/setup/installing-powershell-core-on-linux)

## Install Azure PowerShell for .NET Core

PowerShell Core v6 comes with the PowerShellGet module already installed. This makes it easy to
install any module that is published to the PowerShell Gallery. To install Azure PowerShell, open a
new PowerShell session and run the following command:

```powershell
Install-Module AzureRM.NetCore
```

## Load the AzureRM.Netcore module

Once the module is installed, you need to load the module into your PowerShell session. Modules are
loaded using the `Import-Module` cmdlet, as follows:

```powershell
Import-Module AzureRM.Netcore
Import-Module AzureRM.Profile.Netcore
```

After the import completes, you can test your newly installed and module by attempting to sign into
Azure using the following command:

```powershell
Connect-AzureRmAccount
```

The above command should prompt you to go to `https://aka.ms/devicelogin` and enter the
provided code.

## Available cmdlets

The Azure PowerShell modules for .NET Standard are still in development. These modules do not
provide the full set of cmdlets that are available for the Windows version of the modules. The
following functions are implemented in AzureRM.Netcore modules:

* Account management
  - Login with Microsoft account, Organizational account, or Service Principal through Microsoft
    Azure Active Directory
  - Save Credentials to disk with Save-AzureRmContext and load saved credentials using
    Import-AzureRmContext
* Environment
  - Get the different out-of-box Microsoft Azure environments
  - Add/Set/Remove customized environments (like your Azure Stack or Windows Azure Pack environments)
* Management plane cmdlets for Azure services using Resource Manager and Service Management interfaces.
  - Virtual Machine
  - App Service (Websites)
  - SQL Database
  - Storage
  - Network

## Next Steps

For more information about using Azure PowerShell, see the
[Get started with Azure PowerShell](get-started-azureps.md) article.
