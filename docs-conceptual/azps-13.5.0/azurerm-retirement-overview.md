---
description: Overview of the AzureRM PowerShell module retirement including steps and tools for migrating Azure PowerShell scripts from AzureRM to the Az PowerShell module.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: AzureRM PowerShell module retirement overview
---

# AzureRM PowerShell module retirement overview

All versions of the AzureRM PowerShell module are deprecated. The [Az PowerShell
module](install-azure-powershell.md) is the recommended PowerShell module for interacting with
Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## Why a new module

The launch of the Az PowerShell module represents a significant shift, primarily due to PowerShell's
evolution into a cross-platform tool, thanks to its foundation on the .NET Standard library. This
aligns with our dedication to extend Azure support across various platforms. The transition to .NET
Standard and compatibility with PowerShell Core necessitated an update in our Azure PowerShell
modules. Opting to develop the new Az module instead of overhauling the existing AzureRM module
allowed for a more seamless integration of these changes.

The creation of the Az module also provided an opportunity for our engineers to standardize the
design, naming conventions, and structure of cmdlets and modules. All modules now use the 'Az.'
prefix, and cmdlets follow the 'Verb-AzNoun' format, ensuring consistency and shorter, more
intuitive names compared to the previous longer and varied cmdlet names.

Additionally, the Az module brings a reduction in the number of modules by merging those that manage
similar services. This consolidation, especially the combination of management plane and data plane
cmdlets within a single module, simplifies dependency and import management for users.

These advancements signify our commitment to enhancing user experience and expanding platform
compatibility for Azure PowerShell cmdlets.

## Key Advantages of the Az PowerShell Modules

- **Cross-Platform Compatibility:** Built on the .NET Standard library, it ensures consistent
  performance across different platforms.
- **User-Centric Improvements:** Addresses feedback on command length and reduces inconsistencies in
  cmdlets and modules.
- **Enhanced Security and Stability:** Includes token cache encryption, mitigates certain types of
  cyberattacks, supports various authentication methods including ADFS 2019 and username/password in
  PowerShell 7.
- **Comprehensive Azure Service Support:** Covers all generally available Azure services with
  continual updates, bug fixes, and API version upgrades.
- **Innovative Features:** Available in Cloud Shell and across platforms, it enables access token
  retrieval for Azure resources and provides cmdlets for advanced REST operations.

By adopting the Az PowerShell module, users gain a more secure, stable, and efficient tool for
managing Azure services.

## Next steps

- [Migration Steps](migrate-from-azurerm-to-az.md)
- [Automatically migrate PowerShell scripts](quickstart-migrate-azurerm-to-az-automatically.md)
- [Introducing the Az PowerShell module](new-azureps-module-az.md)
- [Changes between AzureRM and Az](migrate-az-1.0.0.md)
- [Install the Az PowerShell module](install-azure-powershell.md)
- [Uninstall AzureRM](uninstall-az-ps.md#uninstall-the-azurerm-module)
