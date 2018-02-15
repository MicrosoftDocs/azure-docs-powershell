---
title: Azure PowerShell Change Log | Microsoft Docs
description: This is a history of changes made to Azure PowerShell in the latest release.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-powershell
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload:
ms.date: 1/31/2018
---

# Release notes

This is a list of changes made to Azure PowerShell in this release.

---

## 5.3.0 - February 2018
### AzureRM.Profile
* Added deprecation warning for PowerShell 3 and 4
* `Add-AzureRmAccount` has been renamed as `Connect-AzureRmAccount`; an alias has been added for the old cmdlet name, and other aliases (`Login-AzAccount` and `Login-AzureRmAccount`) have been redirected to the new cmdlet name.
* `Remove-AzureRmAccount` has been renamed as `Disconnect-AzureRmAccount`; an alias has been added for the old cmdlet name, and other aliases (`Logout-AzAccount` and `Logout-AzureRmAccount`) have been redirected to the new cmdlet name.
* Corrected Resource Strings to use `Connect-AzureRmAccount` instead of `Login-AzureRmAccount`
* `Add-AzureRmEnvironment` and `Set-AzureRmEnvironment`
  - Added `-AzureOperationalInsightsEndpoint` and `-AzureOperationalInsightsEndpointResourceId` as parameters for use with OperationalInsights data plane RP.  

### AzureRM.AnalysisServices
* Corrected usage of `Login-AzureRmAccount` to use `Connect-AzureRmAccount`

### AzureRM.Compute
* Added `-AvailabilitySetName` parameter to the simplified parameterset of `New-AzureRmVM`.
* Corrected usage of `Login-AzureRmAccount` to use `Connect-AzureRmAccount`
* User assigned identity support for VM and VM scale set
    - `-IdentityType` and `-IdentityId` parameters are added to `New-AzureRmVMConfig`, `New-AzureRmVmssConfig`, `Update-AzureRmVM` and `Update-AzureRmVmss`
* Added `-EnableIPForwarding` parameter to `Add-AzureRmVmssNetworkInterfaceConfig`
* Added `-Priority` parameter to `New-AzureRmVmssConfig`

### AzureRM.DataLakeAnalytics
* Corrected usage of `Login-AzureRmAccount` to use `Connect-AzureRmAccount`

### AzureRM.DataLakeStore
* Corrected usage of `Login-AzureRmAccount` to use `Connect-AzureRmAccount`
* Corrected the error message of `Test-AzureRmDataLakeStoreAccount` when running this cmdlet without having logged in with `Login-AzureRmAccount`

### AzureRM.EventGrid
* Updated to use the 2018-01-01 API version.

### AzureRM.EventHub
* Added below new commands for Geo Disaster Recovery operations.
	-Creating a new Alias(Disaster Recovery configuration):
		- `New-AzureRmEventHubGeoDRConfiguration`
	-Retrieve Alias(Disaster Recovery configuration) :
		- `Get-AzureRmEventHubGeoDRConfiguration`
	-Disabling the Disaster Recovery and stops replicating changes from primary to secondary namespaces
		- `Set-AzureRmEventHubGeoDRConfigurationBreakPair`
	-Invoking Disaster Recovery failover and reconfigure the alias to point to the secondary namespace
		- `Set-AzureRmEventHubGeoDRConfigurationFailOver`
	-Deleting an Alias(Disaster Recovery configuration)
		- `Remove-AzureRmEventHubGeoDRConfiguration`
* Added below new commands for checking the Namespace Name and GeoDr Configuration Name - Alias availability.
	-Check the Availability of Namespace name or Alias(Disaster Recovery configuration) name:
		- `Test-AzureRmEventHubName`

### AzureRM.Insights
* Corrected usage of `Login-AzureRmAccount` to use `Connect-AzureRmAccount`

### AzureRM.KeyVault
* Corrected usage of `Login-AzureRmAccount` to use `Connect-AzureRmAccount`

### AzureRM.Network
* Fix overwrite message 'Are you sure you want to overwriteresource'

#### AzureRM.OperationalInsights
* Added support for V2 API querying via `Invoke-AzureRmOperationalInsightsQuery`. See [https://dev.loganalytics.io/](https://dev.loganalytics.io/) for more info on the new API.

### AzureRM.Resources
* `Get-AzureRmADServicePrincipal`: Removed `-ServicePrincipalName` from the default Empty parameter set as it was redundant with the SPN parameter set

### AzureRM.ServiceBus
* Added functionality fix for `Remove-AzureRmServiceBusRule` and `Get-AzureRmServiceBusKey`
* Added below new commandlets for Geo Disaster Recovery operations.
	-Creating a new Alias(Disaster Recovery configuration):
		- `New-AzureRmServiceBusDRConfigurations`
	-Retrieve Alias(Disaster Recovery configuration) :
		- `Get-AzureRmServiceBusDRConfigurations`
	-Disabling the Disaster Recovery and stops replicating changes from primary to secondary namespaces
		- `Set-AzureRmServiceBusDRConfigurationsBreakPairing`
	-Invoking Disaster Recovery failover and reconfigure the alias to point to the secondary namespace
		- `Set-AzureRmServiceBusDRConfigurationsFailOver`
	-Deleting an Alias(Disaster Recovery configuration)
		- `Remove-AzureRmServiceBusDRConfigurations`
* Updated `Test-AzureRmServiceBusName` commandlets to support Geo Disaster Recovery - Alias name check availability operations.
	-Check the Availability of Namespace name or Alias(Disaster Recovery configuration) name:
		- `Test-AzureRmServiceBusName`

### AzureRM.UsageAggregates
* Corrected usage of `Login-AzureRmAccount` to use `Connect-AzureRmAccount`
