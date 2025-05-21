---
description: Learn how to optimize the installation of Azure PowerShell using PSResourceGet and install only the modules you need.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
title: Optimize the installation of Azure PowerShell
---

# Optimize the installation of Azure PowerShell

This article explores how to optimize the Azure PowerShell installation process by selectively
installing only the modules you need using the **Microsoft.PowerShell.PSResourceGet**
(PSResourceGet) PowerShell module, an improved package management solution introduced with
PowerShell version 7.4.

## Prerequisites

1. On Windows systems, you must set the PowerShell execution policy to remote signed or less
   restrictive

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

1. Determine if the **PSResourceGet** PowerShell module is installed and install it if necessary.
   The **PSResourceGet** module provides improved capabilities for installing PowerShell resources,
   including Azure PowerShell modules. **PSResourceGet** is preinstalled with PowerShell version 7.4
   or higher and is also supported in Windows PowerShell 5.1.

   - Determine if the **PSResourceGet** PowerShell module is installed.

     ```powershell
     Get-Module -Name Microsoft.PowerShell.PSResourceGet -ListAvailable
     ```

   - Install the **PSResourceGet** PowerShell module.

     ```powershell
     Install-Module -Name Microsoft.PowerShell.PSResourceGet -Repository PSGallery
     ```

## The Az PowerShell module

Azure PowerShell is the product name for the collection of official Microsoft PowerShell modules for
managing Azure resources. The **Az** PowerShell module is the current iteration of Azure PowerShell.

The **Az** PowerShell module is a wrapper module for Azure service-related PowerShell modules,
usually one module per Azure service, such as **Az.Compute**, **Az.Network**, and **Az.Storage**.
When you install the **Az** PowerShell module, you install all the generally available (GA) Azure
PowerShell service-specific modules.

Each submodule of the **Az** PowerShell module depends on the **Az.Accounts** module, which provides
the core authentication and account management capabilities for Azure PowerShell. When you use
`Install-Module` (part of **PowerShellGet**) to install the **Az** PowerShell module, the
**Az.Accounts** module is downloaded and installed for each submodule. This redundant download
process increases the installation time.

**PSResourceGet** installs **Az.Accounts** only once, regardless of the number of submodules you
install. This results in a faster, more efficient installation process.

```powershell
Install-PSResource -Name Az
```

## Install individual service-specific modules

Installing the entire **Az** PowerShell module with all the service-specific modules bundled
together is convenient, but time-consuming and inefficient if you only use a subset of its commands.
Installing the entire **Az** PowerShell module results in:

- **Longer installation times**.
- **Increased storage requirements**.
- **Unnecessary updates** for modules you don't use.

You can streamline the process by installing only the service-specific modules you need. The
combination of using **PSResourceGet** and installing only the modules you need dramatically
reduces installation overhead.

The following example uses the `Install-PSResource` cmdlet to install the **Az.Compute**,
**Az.Network**, **Az.Resources**, and **Az.Storage** PowerShell modules.

```powershell
Install-PSResource -Name Az.Compute, Az.Network, Az.Resources, Az.Storage
```

The **Az.Accounts** module is also installed automatically, but only once.

## Install all GA and preview modules

If you need all the general availability (GA) and preview versions of **Az** PowerShell modules,
install the **AzPreview** module. The **AzPreview** PowerShell module mirrors the structure of the
**Az** module but includes all GA and preview modules. For consistency, its version number is the
same as the **Az** module.

The following example installs the **AzPreview** module using **PSResourceGet**.

```powershell
Install-PSResource -Name AzPreview
```

## Install from the Microsoft Artifact Registry

Installing the **Az** PowerShell module from the Microsoft Artifact Registry (MAR) offers faster,
more reliable installations. MAR ensures quick download speeds and a smooth setup process,
minimizing potential issues during installation.

1. If you're using a version of PowerShell earlier than 7.5.0, you must install
   **Microsoft.PowerShell.PSResourceGet** version 1.1.0 or higher

   ```powershell
   Install-Module -Name Microsoft.PowerShell.PSResourceGet -Repository PSGallery
   ```

1. Register MAR as a repository in **PSResourceGet** on your system

   ```powershell
   Register-PSResourceRepository -Name MAR -Uri https://mcr.microsoft.com -ApiVersion ContainerRegistry
   ```

1. Install the **Az** PowerShell Module from MAR using **PSResourceGet**

   ```powershell
   Install-PSResource -Name Az -Repository MAR
   ```

## Benefits of optimizing the installation process

By adopting a more selective and efficient installation process, you:

- **Reduce resource consumption**: Install only what you need, saving disk space.
- **Improve performance**: Avoid redundant downloads and streamline the setup process.
- **Stay agile**: Update and maintain only the modules you actively use.

## See also

- [Install Microsoft.PowerShell.PSResourceGet][install-psresourceget]
- [Install-PSResource][install-psresource]

## Next steps

To learn more about managing your Azure resources with the **Az** PowerShell module, see
[Get Started with Azure PowerShell][get-started-azps].

<!-- link references -->

[execution-policies]: /powershell/module/microsoft.powershell.core/about/about_execution_policies
[install-psresourceget]: /powershell/gallery/powershellget/install-powershellget#install-microsoftpowershellpsresourceget
[install-psresource]: /powershell/module/microsoft.powershell.psresourceget/install-psresource
[get-started-azps]: get-started-azureps.md
