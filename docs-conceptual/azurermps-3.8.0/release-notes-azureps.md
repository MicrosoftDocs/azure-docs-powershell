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
ms.date: 05/18/2017
---

# Release notes

This is a list of changes made to Azure PowerShell in this release.

## Version 3.8.0
* Compute
  - Fix bug in Get-* cmdlets, to allow retrieving multiple pages of data (more than 120 items)
* DataLakeAnalytics
  - Fix help for some commands to have the proper verbage and examples.
* DataLakeStore
  - Add support for head and tail to the `Get-AzureRMDataLakeStoreItemContent` cmdlet. This enables returning the top N or last N new line delimited rows to be displayed.
* HDInsight
  - Added support for RServer cluster type
    + Edgenode VM size can be specified for RServer cluster in New-AzureRmHDInsightCluster or New-AzureRmHDInsightClusterConfig
    + RServer is now a configuration option in Add-AzureRmHDInsightConfigValues. It allows for RStudio flag to be set to indicate that R Studio installation should be done.
* LogicApp
  - Set-AzureRmIntegrationAccountSchema and Set-AzureRmIntegrationAccountMap cmdlets are fixed for the contentlink issue(Both content and contentlink were set resulting in update failure).
* Network
  - Added support for new web application firewall features to Application Gateways
    + Added New-AzureRmApplicationGatewayFirewallDisabledRuleGroupConfig
    + Added Get-AzureRmApplicationGatewayAvailableWafRuleSets (Alias: List-AzureRmApplicationGatewayAvailableWafRuleSets)
    + Updated New-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: Added parameter -RuleSetType -RuleSetVersion and -DisabledRuleGroups
    + Updated Set-AzureRmApplicationGatewayWebApplicationFirewallConfiguration: Added parameter -RuleSetType -RuleSetVersion and -DisabledRuleGroups
  - Added support for IPSec policies to Virtual Network Gateway Connections
  - Added New-AzureRmIpsecPolicy
  - Updated New-AzureRmVirtualNetworkGatewayConnection: Added parameter -IpsecPolicies and -UsePolicyBasedTrafficSelectors
* Profile
  - *Obsolete*: Save-AzureRmProfile is renamed to Save-AzureRmContext, there is an alias to the old cmdlet name, the alias will be removed in the next release.
  - *Obsolete*: Select-AzureRmProfile is renamed to Import-AzureRmContext, there is an alias to the old cmdlet name, the alias will be removed in the next release.
  - The PSAzureContext and PSAzureProfile output types of profile cmdlets will be changed in the next release.
  - The Save-AzureRmContext cmdlet will have no OutputType in the next release.
  - Fix bug in cmdlet common code to use FIPS-compliant algorithm for data hashes: https://github.com/Azure/azure-powershell/issues/3651
* Sql
  - Bug fixes on Azure Failover Group Cmdlets
  - Fix for operation polling
  - Fix GracePeriodWithDataLossHour value when setting FailoverPolicy to Manual
* TrafficManager
  - Support for the Geographic traffic routing method
    + New value 'Geographic' for the TrafficRoutingMethod parameter of New-AzureRmTrafficManagerProfile
    + New parameter 'GeoMapping' for the New-AzureRmTrafficManagerEndpoint and Add-AzureRmTrafficManagerEndpointConfig
    + Fix piping for Get-AzureRmTrafficManagerProfile when it returns a collection of profiles
* ServiceManagement
  - Restart-AzureVM: Added InitiateMaintenance parameter for performing maintenance during VM restart.
  - Get-AzureVM: Added Maintenance Status field.
  - Added new cmdlets to support Recovery Services vault upgrade
    + Test-AzureRecoveryServicesVaultUpgrade
    + Invoke-AzureRecoveryServicesVaultUpgrade
