---
description: Learn how to install and run Azure PowerShell on Windows. You can install Azure PowerShell on Windows with one command.
ms.custom: devx-track-azurepowershell
ms.date: 09/05/2023  
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Install Azure PowerShell on Windows | Microsoft Docs
zone_pivot_group_filename: azure/zone-pivot-groups.json
zone_pivot_groups: install-azps-windows
---

# Install Azure PowerShell on Windows

The Azure PowerShell Az module is a rollup module. Installing the Az PowerShell module downloads the
generally available modules and makes their cmdlets available for use.

The recommended installation method and PowerShell version for the Az PowerShell module:

- Install from the PowerShell Gallery
- Use with PowerShell version 7 or higher

::: zone pivot="windows-psgallery"

This article explains how to install the Az PowerShell module on Windows from the
[PowerShell Gallery](/powershell/scripting/gallery/overview).

## Prerequisites

- Run the following command from PowerShell to determine your PowerShell version:

  ```powershell
  $PSVersionTable.PSVersion
  ```

- Determine if you have the AzureRM PowerShell module installed:

  ```powershell
  Get-Module -Name AzureRM -ListAvailable
  ```

  > [!IMPORTANT]
  > If you have the AzureRM PowerShell module installed, see
  > [Az and AzureRM coexistence](troubleshooting.md#az-and-azurerm-coexistence) before proceeding.

# [PowerShell 7](#tab/powershell)

- Install a supported version of
  [PowerShell version 7 or higher](/powershell/scripting/install/installing-powershell-on-windows)

# [Windows PowerShell](#tab/windowspowershell)

- Update to
   [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)
- Install [.NET Framework 4.7.2 or later](/dotnet/framework/install)
- Update PowerShellGet

   Launch Windows PowerShell 5.1 elevated as an administrator and run the following command to
   update PowerShellGet:

   ```powershell
   Install-Module -Name PowerShellGet -Force
   ```

---

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

## Installation

Use the [Install-Module](/powershell/module/powershellget/install-module) cmdlet to install the Az
PowerShell module:

```powershell
Install-Module -Name Az -Repository PSGallery -Force
```

## Update the Az PowerShell module

Use [Update-Module](/powershell/module/powershellget/update-module) to update to the latest version
of the Az PowerShell module:

```powershell
Update-Module -Name Az -Force
```

Updating the Az PowerShell module using `Update-Module` doesn't remove old versions of the Az
PowerShell module from your system.

## Uninstallation

To remove the Az PowerShell module, see
[Uninstall the Azure PowerShell module](uninstall-az-ps.md).

::: zone-end

::: zone pivot="windows-msi"

This article explains how to install the Az PowerShell module on Windows using an MSI installer. The
MSI installer is provided for environments where the PowerShell Gallery may be blocked by a
firewall, or an offline installer is needed.

> [!IMPORTANT]
> The MSI installation option can only be used to install the Az PowerShell module for use with
> Windows PowerShell 5.1.

## Prerequisites

- Run the following command from PowerShell to determine your PowerShell version:

  ```powershell
  $PSVersionTable.PSVersion
  ```

- Determine if you have the AzureRM PowerShell module installed

  ```powershell
  Get-Module -Name AzureRM -ListAvailable
  ```

  > [!IMPORTANT]
  > If you have the AzureRM PowerShell module installed, see
  > [Az and AzureRM coexistence](troubleshooting.md#az-and-azurerm-coexistence) before proceeding.

- Update to
   [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)
- Install [.NET Framework 4.7.2 or later](/dotnet/framework/install)

- Set the PowerShell script execution to remote signed or less restrictive

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

## Installation and update

The MSI package for Azure PowerShell is available from
[GitHub](https://github.com/Azure/azure-powershell/releases):

1. Visit
   [github.com/Azure/azure-powershell/releases](https://github.com/Azure/azure-powershell/releases)
1. Locate the most recent Az PowerShell module. They are listed chronologically with no name. For example, `9.5.0`
1. Scroll down to the end of the patch notes and click the arrow next to "Assets" to reveal the
   MSI options.
1. Click on the Az-Cmdlets MSI of your choice to start the download

The installer automatically removes older versions of the Az PowerShell module that were installed
using an MSI. The MSI package installs modules in `"${env:ProgramFiles}\WindowsPowerShell\Modules"`

::: zone-end

## Sign in

To start managing your Azure resources with the Az PowerShell module, launch a PowerShell session
and run `Connect-AzAccount` to sign in to Azure:

```azurepowershell
Connect-AzAccount
```

Use your Azure account login credentials to log into the browser window that opens.

You'll need to repeat this step for every new PowerShell session you start. To learn how to persist
your Azure sign-in across PowerShell sessions, see
[Azure PowerShell context objects](context-persistence.md).

## Troubleshooting

For solutions to common installation issues with the Az PowerShell module, see
[Troubleshoot installation problems with the Azure Az PowerShell module](troubleshooting.md#installation).

## Provide feedback

To file an issue about the Az PowerShell module, see:
[file an issue on GitHub](https://github.com/Azure/azure-powershell/issues)

To provide feedback from within a PowerShell session, use the
[Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet.

## Next Steps

To learn more about managing your Azure resources with the Az PowerShell module, see
[Get Started with Azure PowerShell](get-started-azureps.md).
