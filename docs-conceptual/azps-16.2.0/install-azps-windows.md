---
description: Learn how to install and run Azure PowerShell on Windows to manage your Azure resources with PowerShell. Step-by-step guide for seamless installation and updates.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
title: Install Azure PowerShell on Windows
zone_pivot_groups_path: /powershell/azure/zone-pivot-groups.json
zone_pivot_groups: install-azps-windows
---

# Install Azure PowerShell on Windows

The Az PowerShell module is a rollup module. Installing the Az PowerShell module downloads the
generally available modules and makes their cmdlets available for use.

The recommended installation method and PowerShell version for the Az PowerShell module:

- Install from the PowerShell Gallery
- Use with PowerShell version 7 or higher

::: zone pivot="windows-psgallery"

This article explains how to install the Az PowerShell module on Windows from the
[PowerShell Gallery][powershell-gallery].

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
  > [Az and AzureRM coexistence][azurerm-coexistence] before proceeding.

# [PowerShell 7](#tab/powershell)

- Install a supported version of [PowerShell version 7 or higher][install-pwsh]

# [Windows PowerShell](#tab/windowspowershell)

- Update to [Windows PowerShell 5.1][update-powershell51]
- Install [.NET Framework 4.7.2 or later][install-dotnet]
- Update PowerShellGet

  Launch Windows PowerShell 5.1 elevated as an administrator and run the following command to update
  PowerShellGet:

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
  [about_Execution_Policies][execution-policies].

## Installation

Use the [Install-Module][install-module] cmdlet to install the Az PowerShell module:

```powershell
Install-Module -Name Az -Repository PSGallery -Force
```

## Update the Az PowerShell module

Use [Update-Module][update-module] to update to the latest version of the Az PowerShell module:

```powershell
Update-Module -Name Az -Force
```

Updating the Az PowerShell module using `Update-Module` doesn't remove old versions of the Az
PowerShell module from your system.

## Uninstallation

To remove the Az PowerShell module, see [Uninstall the Azure PowerShell module][uninstall-azps].

::: zone-end

::: zone pivot="windows-msi"

This article explains how to install the Az PowerShell module on Windows using an MSI installer. The
MSI installer is provided for environments where the PowerShell Gallery might be blocked by a
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
  > [Az and AzureRM coexistence][azurerm-coexistence] before proceeding.

- Update to [Windows PowerShell 5.1][update-powershell51]
- Install [.NET Framework 4.7.2 or later][install-dotnet]

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
  [about_Execution_Policies][execution-poliicies].

## Installation and update

The MSI package for Azure PowerShell is available from [GitHub][azps-github]:

1. Visit
   [github.com/Azure/azure-powershell/releases][azps-github-releases]
1. Locate the most recent Az PowerShell module. They're listed chronologically with no name. For
   example, `13.3.0`
1. Scroll down to the end of the patch notes and select the arrow next to "Assets" to reveal the MSI
   options.
1. Select the Az-Cmdlets MSI of your choice to start the download

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

You need to repeat this step for every new PowerShell session you start. To learn how to persist
your Azure sign-in across PowerShell sessions, see
[Azure PowerShell context objects][context-persistence].

## Troubleshooting

For solutions to common installation issues with the Az PowerShell module, see
[Troubleshoot installation problems with the Az PowerShell module][troubleshoot-install].

## Provide feedback

To file an issue about the Az PowerShell module, see: [File an issue on GitHub][report-issue]

To provide feedback from within a PowerShell session, use the [Send-Feedback][send-feedback] cmdlet.

## Next Steps

To learn more about managing your Azure resources with the Az PowerShell module, see
[Get Started with Azure PowerShell][get-started].

<!-- link references -->

[powershell-gallery]: /powershell/scripting/gallery/overview
[azurerm-coexistence]: troubleshooting.md#az-and-azurerm-coexistence
[install-pwsh]: /powershell/scripting/install/installing-powershell-on-windows
[update-powershell51]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[install-dotnet]: /dotnet/framework/install
[execution-policies]: /powershell/module/microsoft.powershell.core/about/about_execution_policies
[install-module]: /powershell/module/powershellget/install-module
[update-module]: /powershell/module/powershellget/update-module
[uninstall-azps]: uninstall-az-ps.md
[azps-github-releases]: https://github.com/Azure/azure-powershell/releases
[context-persistence]: context-persistence.md
[troubleshoot-install]: troubleshooting.md#installation
[report-issue]: https://github.com/Azure/azure-powershell/issues
[send-feedback]: /powershell/module/az.accounts/send-feedback
[get-started]: get-started-azureps.md
