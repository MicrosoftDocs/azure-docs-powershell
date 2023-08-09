---
description: Details about the support lifecycle of the Azure PowerShell modules
ms.custom: devx-track-azurepowershell
ms.date: 08/01/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure PowerShell support lifecycle
---

# Azure PowerShell Support Lifecycle

## Az PowerShell modules

The _"Az PowerShell modules"_ consist of the module named _"Az"_ and the dependent modules signed by
_"Microsoft Corporation"_. The Az PowerShell modules are identifiable by their names, that start
with _"Az."_. For the current list of Az PowerShell modules, see
[Azure PowerShell Modules](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md).

The Az PowerShell modules support lifecycle falls under the
[Azure SDK lifecycle policy](https://support.microsoft.com/help/18486). We support the last two
minor versions of the current major version and last minor version of the previous major version of
the Az PowerShell module.

## Supported environments

The following table identifies the supported platforms for the Az, AzureRM, and Azure PowerShell
modules.

- The ![Supported][1] icon indicates supported version combinations of Azure PowerShell and
  PowerShell.
- The ![Out of Support][4] icon indicates version combinations of Azure PowerShell and PowerShell
  that are no longer supported.
- The ![Not Supported][3] icon indicates unsupported version combinations of Azure PowerShell and
  PowerShell.

|        Azure PowerShell        | PowerShell <br/> <= 7.1 | PowerShell <br/> >= 7.2 | Windows PowerShell <br/> 5.1 |
| ------------------------------ | :---------------------: | :---------------------: | :--------------------------: |
| ![Supported][1] Az 10.x        |   ![Not Supported][3]   |     ![Supported][1]     |       ![Supported][1]        |
| ![Supported][1] Az 9.x         |   ![Not Supported][3]   |     ![Supported][1]     |       ![Supported][1]        |
| ![Out of Support][4] <= Az 8.x |  ![Out of Support][4]   |  ![Out of Support][4]   |     ![Out of Support][4]     |
| ![Supported][1] AzureRM 6.13.2 |   ![Not Supported][3]   |   ![Not Supported][3]   |       ![Supported][1]        |
| ![Supported][1] Azure 5.3.1    |   ![Not Supported][3]   |   ![Not Supported][3]   |       ![Supported][1]        |

> [!NOTE]
> PowerShell 6.2 reached its end of life as of September 4, 2020. The Az PowerShell modules are not
> supported on any version of PowerShell 6.

### Information about CVE-2021-26701

The Az PowerShell modules use components affected by security advisory
[CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) which has
been fixed in PowerShell 7.0.6 and 7.1.3. For more information, see
[Microsoft Security Advisory CVE-2021-26701: .NET Core Remote Code Execution Vulnerability](https://github.com/PowerShell/Announcements/issues/23).

Starting with Az 6.0.0, PowerShell 7.0.6 or 7.1.3 or later is required. When the Az.Accounts module
is imported, the following non-blocking message is displayed if an unsupported version of PowerShell
is being used: _"This version of Az.Accounts is only supported on Windows PowerShell 5.1 and
PowerShell 7.0.6 or greater, open
[https://aka.ms/install-powershell](https://aka.ms/install-powershell) to learn how to upgrade. For
further information, go to [https://aka.ms/azpslifecyle](https://aka.ms/azpslifecycle)."_

## AzureRM PowerShell modules

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

To avoid service interruptions, [update your scripts](https://aka.ms/azpsmigrate) that use AzureRM
PowerShell modules to use Az PowerShell modules by February 29, 2024. To automatically update your
scripts, follow the
[quickstart guide](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

<!-- link references -->
[1]: ../../media/shared/check-mark-button_2705.svg
[2]: ../../media/shared/construction-sign_1f6a7.svg
[3]: ../../media/shared/cross-mark_274c.svg
[4]: ../../media/shared/large-yellow-circle_1f7e1.svg
