---
title: Install and configure the Azure PowerShell Service Management module | Microsoft Docs
description: How to install and configure the Azure PowerShell Service Management module.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/16/2023
ms.custom: devx-track-azurepowershell
---

# Installing the Azure PowerShell Service Management module

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

The Azure PowerShell Service Management module is a rollup module. Installing the Azure PowerShell
Service Management module downloads the generally available modules for managing legacy Azure
resources that use Service Management APIs and makes their cmdlets available for use.


## Prerequisites

> [!IMPORTANT]
> The Azure PowerShell Service Management module only works with Windows PowerShell. It is not
> compatible with PowerShell version 6 or higher and does not run on Linux or macOS.

- Run the following command from PowerShell to determine your PowerShell version:

  ```powershell
  $PSVersionTable.PSVersion
  ```

- Update to
   [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)

- Set the PowerShell execution policy to remote signed or less restrictive

  - Check the PowerShell execution policy:

    ```powershell
    Get-ExecutionPolicy -List
    ```

  - Set the PowerShell execution policy to remote signed:

    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    ```

    For more information about execution policies, see
    [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).

- [Update PowerShellGet for Windows PowerShell 5.1](/powershell/gallery/powershellget/update-powershell-51)

## Installation

Use the [Install-Module](/powershell/module/powershellget/install-module) cmdlet to install the
Azure PowerShell Service Management module:

```powershell
Install-Module -Name Azure, Azure.Storage -Repository PSGallery -AllowClobber -Force
```

The Azure PowerShell Service Management module shares dependencies with the Azure PowerShell
Resource Manager modules. If you have installed the Azure PowerShell Resource Manager modules, the
**AllowClobber** parameter as shown in the previous command is required. This allows the existing
shared dependencies to be updated. Without this parameter, installation of the module fails.

After you install the Azure PowerShell Service Management module, import the module:

```powershell
Import-Module -Name Azure
```

## Sign in

To start managing your legacy Azure resources with the Azure PowerShell Service Management module,
launch a PowerShell session and run
[Add-AzureAccount](/powershell/module/servicemanagement/azure/add-azureaccount) to sign in to Azure:

```azurepowershell
Add-AzureAccount
```

After logging into Azure, the Azure PowerShell Service Management module creates a context for the
given session. That context contains the Azure environment, account, tenant, and subscription used
for all cmdlets within that session.

## Troubleshooting

If you receive the error _"The specified module 'Azure.Storage' with version '4.3.0' was not loaded
because no valid module file was found in any module directory."_, you need to install the
Azure.Storage PowerShell module:

```powershell
Install-Module -Name Azure.Storage -Repository PSGallery -AllowClobber -Force
```

If you receive the error _"The 'Install-Module' command was found in the module 'PowerShellGet', but
the module could not be loaded."_, you need to set the PowerShell execution policy to remote signed
or less restrictive:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## See also

For more information about commands in the Azure PowerShell Service Management module, see [the
cmdlet reference documentation](/powershell/module/servicemanagement/azure/).
