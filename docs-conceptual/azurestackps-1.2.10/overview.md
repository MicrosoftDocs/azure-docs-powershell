---
title: Overview of the Azure Stack PowerShell | Microsoft Docs
description: Overview of Azure Stack PowerShell installation and configuration.
author: SnehaGunda
manager: Byronr
ms.product: azure-stack
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.author: sngun
ms.manager: byronr
---

# Azure Stack PowerShell 

Azure Stack requires the following two PowerShell modules:  

1. The Azure Stack compatible **AzureRM** module which is available by installing the **2017-03-09-profile** API Version Profile. The cmdlets installed by using this profile can be used by the Azure Stack cloud administrators and the tenants. To learn about the PowerShell cmdlets that are available in this profile, see the PowerShell reference content for the [1.2.9 version of AzureRM](https://docs.microsoft.com/en-us/powershell/azure/overview?view=azurermps-1.2.9) module.  

2. The **1.2.10** version of the **AzureStack** module. The cmdlets installed by using this module can be used by Azure Stack cloud administrators only. Administrator can perform operations such as manage offers, plans, services, quotas, etc. by using the PowerShell cmdlets provided by this module. To learn about the PowerShell cmdlets available in this module, see the [AzureStackAdmin](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackadmin/?view=azurestackps-1.2.9#azurerm.azurestackadmin) and [AzureStackStorage](https://docs.microsoft.com/en-us/powershell/module/azurerm.azurestackstorage/?view=azurestackps-1.2.9#azurerm.azurestackstorage) Reference content.

## Next Steps

* [Install PowerShell for Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-install?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)
* [Configure PowerShell for use with Azure Stack](https://docs.microsoft.com/en-us/azure/azure-stack/azure-stack-powershell-configure?view=azurestackps-1.2.9&toc=%2fpowershell%2fmodule%2ftoc.json%3fview%3dazurestackps-1.2.9&view=azurestackps-1.2.9)


