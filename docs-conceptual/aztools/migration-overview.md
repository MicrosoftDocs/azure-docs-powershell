---
description: Overview of the Az.Tools.Migration PowerShell module developed and maintained by the Azure PowerShell team but not part of the Az PowerShell module.
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: overview
title: Overview of the Az.Tools.Migration PowerShell module
---

# Overview of the Az.Tools.Migration PowerShell module

The **Az.Tools.Migration** PowerShell module facilitates the transition from the older **AzureRM**
module to the newer **Az** module, which is recommended for Azure management.

> [!IMPORTANT]
> The **AzureRM** PowerShell module is deprecated as of February 29, 2024.

Microsoft introduced **Az.Tools.Migration** in response to customer feedback, particularly
concerning the effort required to update scripts that were originally written for **AzureRM**.
Recognizing that many customers have invested in creating complex scripts for Azure environments,
**Az.Tools.Migration** was created to streamline and automate the migration process, thus reducing
the manual workload and potential for error during script upgrades.

## How to use the Az.Tools.Migration module

The process of using **Az.Tools.Migration** involves several steps:

1. **Updating to AzureRM version 6.13.1:** Before using **Az.Tools.Migration**, users must ensure
   their scripts are updated to **AzureRM** version 6.13.1, the last version before the migration to
   the **Az** module.

1. **Installing Az.Tools.Migration:** The module can be installed from the PowerShell Gallery with
   the `Install-Module -Name Az.Tools.Migration` command.

1. **Generating an Upgrade Plan:** The `New-AzUpgradeModulePlan` cmdlet generates an upgrade plan.
   It does not change existing scripts but provides an upgrade path by creating a plan detailing
   specific files and offset points requiring updates. This cmdlet takes parameters such as
   **FilePath** and **DirectoryPath** to target specific scripts or folders.

1. **Reviewing the Upgrade Plan:** Before executing the upgrade, it is crucial to review the plan
   for any potential issues that may prevent automatic upgrades, such as commands that use
   splatting, and correct them manually if necessary.

1. **Performing the Upgrade**: After reviewing and resolving any issues, the actual upgrade is
   performed using the `Invoke-AzUpgradeModulePlan` cmdlet. This cmdlet can either modify existing
   files or, more safely, save changes to new files with `_az_upgraded` appended to their names to
   preserve the original scripts.

To ensure a smooth migration, it’s recommended to back up scripts before performing upgrades since
the `Invoke-AzUpgradeModulePlan` cmdlet can be destructive if not used with the
`-FileEditMode SaveChangesToNewFiles` option.

Users are encouraged to provide feedback or report issues with the migration process on [the GitHub
repository for azure-powershell-migration][az-tools-migration-repo].

<!-- link references -->

[az-tools-migration-repo]: https://github.com/Azure/azure-powershell-migration/
