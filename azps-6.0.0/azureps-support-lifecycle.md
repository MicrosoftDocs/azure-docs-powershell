---
title: Azure PowerShell support lifecycle
description: Details about the support lifecycle of the Azure PowerShell modules
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/19/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Azure PowerShell modules Lifecycle

## Az modules

The "Az modules" comprises the module named "Az" and the dependent modules signed by “Microsoft
Corporation” (identifiable with names starting with “Az.”). The current list of Az modules is
available on
[this page](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md)

The Az modules support lifecycle falls under the (Azure SDK lifecycle
policy)[https://support.microsoft.com/en-us/help/18486], we are supporting no less than the last
minor version of each of the two most recent major versions of the Az module.

## AzureRM modules

Because Az PowerShell modules now have all the capabilities of AzureRM PowerShell modules and more,
we'll retire AzureRM PowerShell modules on 29 February 2024.

To avoid service interruptions, [update your scripts](https://aka.ms/azpsmigrate) that use AzureRM
PowerShell modules to use Az PowerShell modules by 29 February 2024. To automatically update your
scripts, follow the [quickstart guide](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## Supported environments

The following table identifies the supported platforms for the Az and Azure modules.

| Az | PowerShell <br/> 7.1.3 | PowerShell <br/> >= 7.0.6 | PowerShell <br/> =< 7.0.5 | Windows PowerShell <br/> 5.1 |
| :--------------: | :-----------: | :-----------: | :-----------: | :--------:|
| Az 6.0           | Supported     | Supported     | Not supported | Supported |
| Az 5.9           | Supported     | Supported     | Supported     | Supported |
| Az 4.8           | Supported     | Supported     | Supported     | Supported |
| AzureRM (6.13.2) | Supported     | Supported     | Supported     | Supported |
| Azure (5.3.0)    | Not Supported | Not Supported | Not Supported | Supported |

[!NOTE] PowerShell 6.2 has reached its end of live as of September 4, 2020. The Az PowerShell
modules are not supported on any versions of PowerShell 6.

### Information about CVE-2021-26701

Az PowerShell modules use the components impacted by the security advisory
[CVE-2021-26701](https://msrc.microsoft.com/update-guide/en-us/vulnerability/CVE-2021-26701) which
has been fixed in PowerShell 7.0.6 and 7.1.3 (more information on this page
[this page](https://github.com/PowerShell/Announcements/issues/23).

Starting with Az 6.0.0, PowerShell 7.0.6 or 7.1.3 or later is required to be supported. When
Az.Accounts module is imported, the following non-blocking message will be displayed: "This version
of Az.Accounts is only supported on Windows PowerShell 5.1 and PowerShell 7.0.6 or greater, open
https://aka.ms/install-powershell to learn how to upgrade. For further information, go to  
https://aka.ms/azpslifecyle."
