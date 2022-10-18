---
description: This migration guide contains a list of breaking changes made to Azure PowerShell in the Az version 9.0.0 release.
ms.custom: devx-track-azurepowershell
ms.date: 10/18/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Migration guide for Az 9.0.0
---

# Migration Guide for Az 9.0.0

This document describes the changes between the 8.0.0 and 9.0.0 versions of Az.

- [Migration Guide for Az 9.0.0](#migration-guide-for-az-900)
  - [Az.Advisor](#azadvisor)
    - [`Set-AzAdvisorConfiguration`](#set-azadvisorconfiguration)
    - [`Enable-AzAdvisorRecommendation`](#enable-azadvisorrecommendation)
    - [`Disable-AzAdvisorRecommendation`](#disable-azadvisorrecommendation)
    - [`Get-AzAdvisorRecommendation`](#get-azadvisorrecommendation)
    - [`Get-AzAdvisorConfiguration`](#get-azadvisorconfiguration)
  - [Az.Aks](#azaks)
    - [`Install-AzAksCliTool`](#install-azaksclitool)
  - [Az.ApiManagement](#azapimanagement)
    - [`Get-AzApiManagement`](#get-azapimanagement)
    - [`Set-AzApiManagement`](#set-azapimanagement)
    - [`Restore-AzApiManagement`](#restore-azapimanagement)
    - [`Get-AzApiManagementSsoToken`](#get-azapimanagementssotoken)
    - [`Update-AzApiManagementRegion`](#update-azapimanagementregion)
    - [`Backup-AzApiManagement`](#backup-azapimanagement)
    - [`Add-AzApiManagementRegion`](#add-azapimanagementregion)
    - [`New-AzApiManagement`](#new-azapimanagement)
    - [`New-AzApiManagementRegion`](#new-azapimanagementregion)
    - [`Remove-AzApiManagementRegion`](#remove-azapimanagementregion)
    - [`Get-AzApiManagementNetworkStatus`](#get-azapimanagementnetworkstatus)
  - [Az.Attestation](#azattestation)
    - [`New-AzAttestation`](#new-azattestation)
    - [`Remove-AzAttestation`](#remove-azattestation)
    - [`Get-AzAttestation`](#get-azattestation)
  - [Az.EventHub](#azeventhub)
    - [`Set-AzEventHubConsumerGroup`](#set-azeventhubconsumergroup)
    - [`Remove-AzEventHubAuthorizationRule`](#remove-azeventhubauthorizationrule)
    - [`Get-AzEventHubAuthorizationRule`](#get-azeventhubauthorizationrule)
    - [`Get-AzEventHubNetworkRuleSet`](#get-azeventhubnetworkruleset)
    - [`Set-AzEventHubNetworkRuleSet`](#set-azeventhubnetworkruleset)
    - [`Get-AzEventHubClustersAvailableRegion`](#get-azeventhubclustersavailableregion)
    - [`Remove-AzEventHubPrivateEndpointConnection`](#remove-azeventhubprivateendpointconnection)
    - [`Get-AzEventHubCluster`](#get-azeventhubcluster)
    - [`Set-AzEventHubGeoDRConfigurationBreakPair`](#set-azeventhubgeodrconfigurationbreakpair)
    - [`Remove-AzEventHubConsumerGroup`](#remove-azeventhubconsumergroup)
    - [`Approve-AzEventHubPrivateEndpointConnection`](#approve-azeventhubprivateendpointconnection)
    - [`Deny-AzEventHubPrivateEndpointConnection`](#deny-azeventhubprivateendpointconnection)
    - [`New-AzEventHubAuthorizationRule`](#new-azeventhubauthorizationrule)
    - [`Set-AzEventHubAuthorizationRule`](#set-azeventhubauthorizationrule)
    - [`Remove-AzEventHubCluster`](#remove-azeventhubcluster)
    - [`Get-AzEventHubApplicationGroup`](#get-azeventhubapplicationgroup)
    - [`Get-AzEventHub`](#get-azeventhub)
    - [`Remove-AzEventHub`](#remove-azeventhub)
    - [`Set-AzEventHubApplicationGroup`](#set-azeventhubapplicationgroup)
    - [`Get-AzEventHubConsumerGroup`](#get-azeventhubconsumergroup)
    - [`New-AzEventHubSchemaGroup`](#new-azeventhubschemagroup)
    - [`Remove-AzEventHubApplicationGroup`](#remove-azeventhubapplicationgroup)
    - [`New-AzEventHubCluster`](#new-azeventhubcluster)
    - [`Get-AzEventHubPrivateLink`](#get-azeventhubprivatelink)
    - [`New-AzEventHubKey`](#new-azeventhubkey)
    - [`New-AzEventHubThrottlingPolicyConfig`](#new-azeventhubthrottlingpolicyconfig)
    - [`New-AzEventHubConsumerGroup`](#new-azeventhubconsumergroup)
    - [`Set-AzEventHub`](#set-azeventhub)
    - [`Get-AzEventHubSchemaGroup`](#get-azeventhubschemagroup)
    - [`Get-AzEventHubPrivateEndpointConnection`](#get-azeventhubprivateendpointconnection)
    - [`Set-AzEventHubCluster`](#set-azeventhubcluster)
    - [`New-AzEventHub`](#new-azeventhub)
    - [`New-AzEventHubApplicationGroup`](#new-azeventhubapplicationgroup)
    - [`Remove-AzEventHubGeoDRConfiguration`](#remove-azeventhubgeodrconfiguration)
    - [`Test-AzEventHubName`](#test-azeventhubname)
    - [`Set-AzEventHubGeoDRConfigurationFailOver`](#set-azeventhubgeodrconfigurationfailover)
    - [`New-AzEventHubGeoDRConfiguration`](#new-azeventhubgeodrconfiguration)
    - [`Remove-AzEventHubSchemaGroup`](#remove-azeventhubschemagroup)
    - [`Get-AzEventHubGeoDRConfiguration`](#get-azeventhubgeodrconfiguration)
    - [`Get-AzEventHubKey`](#get-azeventhubkey)
  - [Az.MarketplaceOrdering](#azmarketplaceordering)
    - [`Get-AzMarketplaceTerms`](#get-azmarketplaceterms)
    - [`Set-AzMarketplaceTerms`](#set-azmarketplaceterms)
  - [Az.Migrate](#azmigrate)
    - [`New-AzMigrateReplicationVaultSetting`](#new-azmigratereplicationvaultsetting)
    - [`Get-AzMigrateReplicationVaultSetting`](#get-azmigratereplicationvaultsetting)
    - [`Get-AzMigrateReplicationProtectionIntent`](#get-azmigratereplicationprotectionintent)
    - [`Get-AzMigrateSupportedOperatingSystem`](#get-azmigratesupportedoperatingsystem)
    - [`Get-AzMigrateReplicationEligibilityResult`](#get-azmigratereplicationeligibilityresult)
    - [`New-AzMigrateReplicationProtectionIntent`](#new-azmigratereplicationprotectionintent)
  - [Az.Monitor](#azmonitor)
    - [`Get-AzAutoscaleSetting`](#get-azautoscalesetting)
    - [`Get-AzSubscriptionDiagnosticSettingCategory`](#get-azsubscriptiondiagnosticsettingcategory)
    - [`Remove-AzAutoscaleSetting`](#remove-azautoscalesetting)
    - [`New-AzAutoscaleProfile`](#new-azautoscaleprofile)
    - [`Remove-AzDiagnosticSetting`](#remove-azdiagnosticsetting)
    - [`New-AzDiagnosticSetting`](#new-azdiagnosticsetting)
    - [`New-AzScheduledQueryRule`](#new-azscheduledqueryrule)
    - [`New-AzScheduledQueryRuleAznsActionGroup`](#new-azscheduledqueryruleaznsactiongroup)
    - [`Set-AzScheduledQueryRule`](#set-azscheduledqueryrule)
    - [`New-AzScheduledQueryRuleSource`](#new-azscheduledqueryrulesource)
    - [`New-AzScheduledQueryRuleLogMetricTrigger`](#new-azscheduledqueryrulelogmetrictrigger)
    - [`Enable-AzActivityLogAlert`](#enable-azactivitylogalert)
    - [`New-AzAutoscaleNotification`](#new-azautoscalenotification)
    - [`New-AzActionGroup`](#new-azactiongroup)
    - [`New-AzDiagnosticDetailSetting`](#new-azdiagnosticdetailsetting)
    - [`New-AzAutoscaleRule`](#new-azautoscalerule)
    - [`New-AzScheduledQueryRuleSchedule`](#new-azscheduledqueryruleschedule)
    - [`Remove-AzActivityLogAlert`](#remove-azactivitylogalert)
    - [`New-AzAutoscaleWebhook`](#new-azautoscalewebhook)
    - [`Remove-AzScheduledQueryRule`](#remove-azscheduledqueryrule)
    - [`Disable-AzActivityLogAlert`](#disable-azactivitylogalert)
    - [`Set-AzDiagnosticSetting`](#set-azdiagnosticsetting)
    - [`Get-AzScheduledQueryRule`](#get-azscheduledqueryrule)
    - [`Add-AzAutoscaleSetting`](#add-azautoscalesetting)
    - [`Update-AzScheduledQueryRule`](#update-azscheduledqueryrule)
    - [`Get-AzDiagnosticSetting`](#get-azdiagnosticsetting)
    - [`Get-AzDiagnosticSettingCategory`](#get-azdiagnosticsettingcategory)
    - [`New-AzScheduledQueryRuleAlertingAction`](#new-azscheduledqueryrulealertingaction)
    - [`New-AzActivityLogAlertCondition`](#new-azactivitylogalertcondition)
    - [`Set-AzActivityLogAlert`](#set-azactivitylogalert)
    - [`Get-AzActivityLogAlert`](#get-azactivitylogalert)
    - [`New-AzScheduledQueryRuleTriggerCondition`](#new-azscheduledqueryruletriggercondition)
  - [Az.Network](#aznetwork)
    - [`New-AzFirewall`](#new-azfirewall)
    - [`New-AzFirewallHubIpAddress`](#new-azfirewallhubipaddress)
    - [`Set-AzFirewall`](#set-azfirewall)
    - [`New-AzNetworkManagerAddressPrefixItem`](#new-aznetworkmanageraddressprefixitem)
    - [`New-AzNetworkManagerSecurityAdminConfiguration`](#new-aznetworkmanagersecurityadminconfiguration)
    - [`New-AzNetworkManager`](#new-aznetworkmanager)
    - [`Get-AzFirewall`](#get-azfirewall)
    - [`New-AzNetworkManagerConnectivityConfiguration`](#new-aznetworkmanagerconnectivityconfiguration)
    - [`Deploy-AzNetworkManagerCommit`](#deploy-aznetworkmanagercommit)
    - [`New-AzNetworkManagerConnectivityGroupItem`](#new-aznetworkmanagerconnectivitygroupitem)
    - [`New-AzNetworkManagerSecurityAdminRule`](#new-aznetworkmanagersecurityadminrule)
  - [Az.RecoveryServices](#azrecoveryservices)
    - [`Get-AzRecoveryServicesBackupContainer`](#get-azrecoveryservicesbackupcontainer)
  - [Az.SecurityInsights](#azsecurityinsights)
    - [`Update-AzSentinelAlertRuleAction`](#update-azsentinelalertruleaction)
    - [`New-AzSentinelIncidentOwner`](#new-azsentinelincidentowner)
    - [`New-AzSentinelIncidentComment`](#new-azsentinelincidentcomment)
    - [`Get-AzSentinelBookmark`](#get-azsentinelbookmark)
    - [`Update-AzSentinelAlertRule`](#update-azsentinelalertrule)
    - [`Get-AzSentinelIncidentComment`](#get-azsentinelincidentcomment)
    - [`Get-AzSentinelAlertRuleAction`](#get-azsentinelalertruleaction)
    - [`Remove-AzSentinelIncident`](#remove-azsentinelincident)
    - [`New-AzSentinelBookmark`](#new-azsentinelbookmark)
    - [`Remove-AzSentinelAlertRule`](#remove-azsentinelalertrule)
    - [`Remove-AzSentinelAlertRuleAction`](#remove-azsentinelalertruleaction)
    - [`Get-AzSentinelAlertRule`](#get-azsentinelalertrule)
    - [`Update-AzSentinelDataConnector`](#update-azsentineldataconnector)
    - [`Remove-AzSentinelBookmark`](#remove-azsentinelbookmark)
    - [`New-AzSentinelIncident`](#new-azsentinelincident)
    - [`New-AzSentinelAlertRuleAction`](#new-azsentinelalertruleaction)
    - [`Get-AzSentinelIncident`](#get-azsentinelincident)
    - [`Remove-AzSentinelDataConnector`](#remove-azsentineldataconnector)
    - [`New-AzSentinelDataConnector`](#new-azsentineldataconnector)
    - [`New-AzSentinelAlertRule`](#new-azsentinelalertrule)
    - [`Get-AzSentinelAlertRuleTemplate`](#get-azsentinelalertruletemplate)
    - [`Update-AzSentinelIncident`](#update-azsentinelincident)
    - [`Get-AzSentinelDataConnector`](#get-azsentineldataconnector)
    - [`Update-AzSentinelBookmark`](#update-azsentinelbookmark)
  - [Az.ServiceBus](#azservicebus)
    - [`Set-AzServiceBusGeoDRConfigurationBreakPair`](#set-azservicebusgeodrconfigurationbreakpair)
    - [`Remove-AzServiceBusGeoDRConfiguration`](#remove-azservicebusgeodrconfiguration)
    - [`Set-AzServiceBusTopic`](#set-azservicebustopic)
    - [`New-AzServiceBusTopic`](#new-azservicebustopic)
    - [`Get-AzServiceBusTopic`](#get-azservicebustopic)
    - [`Remove-AzServiceBusQueue`](#remove-azservicebusqueue)
    - [`Remove-AzServiceBusMigration`](#remove-azservicebusmigration)
    - [`New-AzServiceBusRule`](#new-azservicebusrule)
    - [`Approve-AzServiceBusPrivateEndpointConnection`](#approve-azservicebusprivateendpointconnection)
    - [`Stop-AzServiceBusMigration`](#stop-azservicebusmigration)
    - [`Get-AzServiceBusMigration`](#get-azservicebusmigration)
    - [`Remove-AzServiceBusTopic`](#remove-azservicebustopic)
    - [`Set-AzServiceBusRule`](#set-azservicebusrule)
    - [`Get-AzServiceBusKey`](#get-azservicebuskey)
    - [`Set-AzServiceBusGeoDRConfigurationFailOver`](#set-azservicebusgeodrconfigurationfailover)
    - [`New-AzServiceBusKey`](#new-azservicebuskey)
    - [`Remove-AzServiceBusSubscription`](#remove-azservicebussubscription)
    - [`Get-AzServiceBusRule`](#get-azservicebusrule)
    - [`New-AzServiceBusQueue`](#new-azservicebusqueue)
    - [`Set-AzServiceBusQueue`](#set-azservicebusqueue)
    - [`Get-AzServiceBusNetworkRuleSet`](#get-azservicebusnetworkruleset)
    - [`Deny-AzServiceBusPrivateEndpointConnection`](#deny-azservicebusprivateendpointconnection)
    - [`Get-AzServiceBusPrivateEndpointConnection`](#get-azservicebusprivateendpointconnection)
    - [`Set-AzServiceBusAuthorizationRule`](#set-azservicebusauthorizationrule)
    - [`Remove-AzServiceBusAuthorizationRule`](#remove-azservicebusauthorizationrule)
    - [`Get-AzServiceBusSubscription`](#get-azservicebussubscription)
    - [`Start-AzServiceBusMigration`](#start-azservicebusmigration)
    - [`Test-AzServiceBusName`](#test-azservicebusname)
    - [`Get-AzServiceBusQueue`](#get-azservicebusqueue)
    - [`Get-AzServiceBusGeoDRConfiguration`](#get-azservicebusgeodrconfiguration)
    - [`Remove-AzServiceBusRule`](#remove-azservicebusrule)
    - [`New-AzServiceBusAuthorizationRule`](#new-azservicebusauthorizationrule)
    - [`Complete-AzServiceBusMigration`](#complete-azservicebusmigration)
    - [`Set-AzServiceBusNetworkRuleSet`](#set-azservicebusnetworkruleset)
    - [`New-AzServiceBusSubscription`](#new-azservicebussubscription)
    - [`Set-AzServiceBusSubscription`](#set-azservicebussubscription)
    - [`Get-AzServiceBusPrivateLink`](#get-azservicebusprivatelink)
    - [`Get-AzServiceBusAuthorizationRule`](#get-azservicebusauthorizationrule)
    - [`New-AzServiceBusGeoDRConfiguration`](#new-azservicebusgeodrconfiguration)
    - [`Remove-AzServiceBusPrivateEndpointConnection`](#remove-azservicebusprivateendpointconnection)
  - [Az.Sql](#azsql)
    - [`Update-AzSqlServerAdvancedThreatProtectionSetting`](#update-azsqlserveradvancedthreatprotectionsetting)
    - [`Get-AzSqlServerAdvancedThreatProtectionSetting`](#get-azsqlserveradvancedthreatprotectionsetting)
    - [`Clear-AzSqlDatabaseAdvancedThreatProtectionSetting`](#clear-azsqldatabaseadvancedthreatprotectionsetting)
    - [`Update-AzSqlDatabaseAdvancedThreatProtectionSetting`](#update-azsqldatabaseadvancedthreatprotectionsetting)
    - [`Clear-AzSqlServerAdvancedThreatProtectionSetting`](#clear-azsqlserveradvancedthreatprotectionsetting)
    - [`Disable-AzSqlServerAdvancedDataSecurity`](#disable-azsqlserveradvanceddatasecurity)
    - [`Get-AzSqlDatabaseAdvancedThreatProtectionSetting`](#get-azsqldatabaseadvancedthreatprotectionsetting)
    - [`Enable-AzSqlServerAdvancedDataSecurity`](#enable-azsqlserveradvanceddatasecurity)
  - [Az.Storage](#azstorage)
    - [`Get-AzStorageFileCopyState`](#get-azstoragefilecopystate)
  - [Az.Synapse](#azsynapse)
    - [`Get-AzSynapseLinkConnectionLinkTableStatus`](#get-azsynapselinkconnectionlinktablestatus)
    - [`Remove-AzSynapseLinkConnection`](#remove-azsynapselinkconnection)
    - [`Update-AzSynapseLinkConnectionLandingZoneCredential`](#update-azsynapselinkconnectionlandingzonecredential)
    - [`Get-AzSynapseLinkConnectionLinkTable`](#get-azsynapselinkconnectionlinktable)
    - [`Stop-AzSynapseLinkConnection`](#stop-azsynapselinkconnection)
    - [`Set-AzSynapseLinkConnection`](#set-azsynapselinkconnection)
    - [`Get-AzSynapseLinkConnection`](#get-azsynapselinkconnection)
    - [`Start-AzSynapseLinkConnection`](#start-azsynapselinkconnection)
    - [`Set-AzSynapseLinkConnectionLinkTable`](#set-azsynapselinkconnectionlinktable)

## Az.Advisor

### `Set-AzAdvisorConfiguration`

The cmdlet 'Set-AzAdvisorConfiguration' no longer has output type 'Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorConfigurationData'.
The parameter set 'InputObjectRgExcludeParameterSet' for cmdlet 'Set-AzAdvisorConfiguration' is no longer the default parameter set.
The parameter set 'InputObjectRgExcludeParameterSet' for cmdlet 'Set-AzAdvisorConfiguration' is no longer the default parameter set.
The cmdlet 'Set-AzAdvisorConfiguration' no longer supports the type 'System.Int32' for parameter 'LowCpuThreshold'.
The cmdlet 'Set-AzAdvisorConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorConfigurationData' for parameter 'InputObject'.
The cmdlet 'Set-AzAdvisorConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzAdvisorConfiguration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzAdvisorConfiguration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'InputObjectLowCpuExcludeParameterSet' for cmdlet 'Set-AzAdvisorConfiguration' has been removed.
The parameter set 'InputObjectRgExcludeParameterSet' for cmdlet 'Set-AzAdvisorConfiguration' has been removed.

### `Enable-AzAdvisorRecommendation`
The cmdlet 'Enable-AzAdvisorRecommendation' no longer has output type 'Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorResourceRecommendationBase'.
The parameter set 'NameParameterSet' for cmdlet 'Enable-AzAdvisorRecommendation' is no longer the default parameter set.
The cmdlet 'Enable-AzAdvisorRecommendation' no longer supports the type 'Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorResourceRecommendationBase' for parameter 'InputObject'.
The cmdlet 'Enable-AzAdvisorRecommendation' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Enable-AzAdvisorRecommendation' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Enable-AzAdvisorRecommendation' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'IdParameterSet' for cmdlet 'Enable-AzAdvisorRecommendation' has been removed.
The parameter set 'InputObjectParameterSet' for cmdlet 'Enable-AzAdvisorRecommendation' has been removed.
The parameter set 'NameParameterSet' for cmdlet 'Enable-AzAdvisorRecommendation' has been removed.

### `Disable-AzAdvisorRecommendation`
The cmdlet 'Disable-AzAdvisorRecommendation' no longer has output type 'Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorSuppressionContract'.
The cmdlet 'Disable-AzAdvisorRecommendation' no longer supports the parameter 'Days' and no alias was found for the original parameter name.
The cmdlet 'Disable-AzAdvisorRecommendation' no longer supports the type 'Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorResourceRecommendationBase' for parameter 'InputObject'.
The cmdlet 'Disable-AzAdvisorRecommendation' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Disable-AzAdvisorRecommendation' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Disable-AzAdvisorRecommendation' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'IdParameterSet' for cmdlet 'Disable-AzAdvisorRecommendation' has been removed.
The parameter set 'NameParameterSet' for cmdlet 'Disable-AzAdvisorRecommendation' has been removed.
The parameter set 'InputObjectParameterSet' for cmdlet 'Disable-AzAdvisorRecommendation' has been removed.

### `Get-AzAdvisorRecommendation`
The cmdlet 'Get-AzAdvisorRecommendation' no longer has output type 'Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorResourceRecommendationBase'.
The parameter set 'NameParameterSet' for cmdlet 'Get-AzAdvisorRecommendation' is no longer the default parameter set.
The parameter set 'NameParameterSet' for cmdlet 'Get-AzAdvisorRecommendation' is no longer the default parameter set.
The cmdlet 'Get-AzAdvisorRecommendation' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzAdvisorRecommendation' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzAdvisorRecommendation' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'IdParameterSet' for cmdlet 'Get-AzAdvisorRecommendation' has been removed.
The parameter set 'NameParameterSet' for cmdlet 'Get-AzAdvisorRecommendation' has been removed.

### `Get-AzAdvisorConfiguration`
The cmdlet 'Get-AzAdvisorConfiguration' no longer has output type 'Microsoft.Azure.Commands.Advisor.Cmdlets.Models.PsAzureAdvisorConfigurationData'.
The cmdlet 'Get-AzAdvisorConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzAdvisorConfiguration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzAdvisorConfiguration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'RgParameterSet' for cmdlet 'Get-AzAdvisorConfiguration' has been removed.

## Az.Aks

### `Install-AzAksCliTool`
The cmdlet 'Install-AzAksCliTool' no longer supports the alias 'Install-AzAksKubectl'.

## Az.ApiManagement

### `Get-AzApiManagement`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.

### `Set-AzApiManagement`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.

### `Restore-AzApiManagement`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.

### `Get-AzApiManagementSsoToken`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.

### `Update-AzApiManagementRegion`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.
The cmdlet 'Update-AzApiManagementRegion' no longer supports the type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' for parameter 'Sku'.

### `Backup-AzApiManagement`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.

### `Add-AzApiManagementRegion`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.
The cmdlet 'Add-AzApiManagementRegion' no longer supports the type 'System.Nullable`1[Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku]' for parameter 'Sku'.

### `New-AzApiManagement`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.
The cmdlet 'New-AzApiManagement' no longer supports the type 'System.Nullable`1[Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku]' for parameter 'Sku'.

### `New-AzApiManagementRegion`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.

### `Remove-AzApiManagementRegion`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.

### `Get-AzApiManagementNetworkStatus`
The type of property 'Sku' of type 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement' has changed from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'System.String'.

## Az.Attestation

### `New-AzAttestation`
The cmdlet 'New-AzAttestation' has been removed and no alias was found for the original cmdlet name.

### `Remove-AzAttestation`
The cmdlet 'Remove-AzAttestation' has been removed and no alias was found for the original cmdlet name.

### `Get-AzAttestation`
The cmdlet 'Get-AzAttestation' has been removed and no alias was found for the original cmdlet name.

## Az.EventHub

### `Set-AzEventHubConsumerGroup`
The cmdlet 'Set-AzEventHubConsumerGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSConsumerGroupAttributes'.
The cmdlet 'Set-AzEventHubConsumerGroup' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubConsumerGroup' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubConsumerGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubConsumerGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubConsumerGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzEventHubConsumerGroup' has been removed.

### `Remove-AzEventHubAuthorizationRule`
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzEventHubAuthorizationRule' is no longer the default parameter set.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzEventHubAuthorizationRule' is no longer the default parameter set.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzEventHubAuthorizationRule' is no longer the default parameter set.
The cmdlet 'Remove-AzEventHubAuthorizationRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubAuthorizationRule' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubAuthorizationRule' no longer supports the parameter 'Force' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubAuthorizationRule' no longer supports the parameter 'PassThru' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubAuthorizationRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubAuthorizationRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzEventHubAuthorizationRule' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzEventHubAuthorizationRule' has been removed.
The parameter set 'EventhubAuthorizationRuleSet' for cmdlet 'Remove-AzEventHubAuthorizationRule' has been removed.

### `Get-AzEventHubAuthorizationRule`
The cmdlet 'Get-AzEventHubAuthorizationRule' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSSharedAccessAuthorizationRuleAttributes'.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Get-AzEventHubAuthorizationRule' is no longer the default parameter set.
The cmdlet 'Get-AzEventHubAuthorizationRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubAuthorizationRule' no longer supports the parameter 'Eventhub' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubAuthorizationRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubAuthorizationRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzEventHubAuthorizationRule' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Get-AzEventHubAuthorizationRule' has been removed.
The parameter set 'EventhubAuthorizationRuleSet' for cmdlet 'Get-AzEventHubAuthorizationRule' has been removed.
The parameter set 'AliasAuthoRuleSet' for cmdlet 'Get-AzEventHubAuthorizationRule' has been removed.

### `Get-AzEventHubNetworkRuleSet`
The cmdlet 'Get-AzEventHubNetworkRuleSet' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSNetworkRuleSetAttributes'.
The parameter set 'NetworkRuleSetPropertiesSet' for cmdlet 'Get-AzEventHubNetworkRuleSet' is no longer the default parameter set.
The cmdlet 'Get-AzEventHubNetworkRuleSet' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubNetworkRuleSet' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubNetworkRuleSet' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubNetworkRuleSet' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubNetworkRuleSet' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'NetworkRuleSetPropertiesSet' for cmdlet 'Get-AzEventHubNetworkRuleSet' has been removed.
The parameter set 'NetworkRuleSetNamespacePropertiesSet' for cmdlet 'Get-AzEventHubNetworkRuleSet' has been removed.
The parameter set 'NetworkRuleSetResourceIdParameterSet' for cmdlet 'Get-AzEventHubNetworkRuleSet' has been removed.

### `Set-AzEventHubNetworkRuleSet`
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSNetworkRuleSetAttributes'.
The parameter set 'NetworkRuleSetPropertiesSet' for cmdlet 'Set-AzEventHubNetworkRuleSet' is no longer the default parameter set.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the parameter 'Name' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the type 'System.String' for parameter 'DefaultAction'.
The element type for parameter 'IPRule' has been changed from 'Microsoft.Azure.Commands.EventHub.Models.PSNWRuleSetIpRulesAttributes' to 'Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.INwRuleSetIPRules'.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the type 'System.String' for parameter 'PublicNetworkAccess'.
The element type for parameter 'VirtualNetworkRule' has been changed from 'Microsoft.Azure.Commands.EventHub.Models.PSNWRuleSetVirtualNetworkRulesAttributes' to 'Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.INwRuleSetVirtualNetworkRules'.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the alias 'VirtualNteworkRule' for parameter 'VirtualNetworkRule'.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSNetworkRuleSetAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubNetworkRuleSet' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'NetwrokruleSetInputObjectSet' for cmdlet 'Set-AzEventHubNetworkRuleSet' has been removed.
The parameter set 'NetworkRuleSetPropertiesSet' for cmdlet 'Set-AzEventHubNetworkRuleSet' has been removed.
The parameter set 'NetworkRuleSetResourceIdParameterSet' for cmdlet 'Set-AzEventHubNetworkRuleSet' has been removed.

### `Get-AzEventHubClustersAvailableRegion`
The cmdlet 'Get-AzEventHubClustersAvailableRegion' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubClustersAvailableRegion' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubClustersAvailableRegion' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.

### `Remove-AzEventHubPrivateEndpointConnection`
The cmdlet 'Remove-AzEventHubPrivateEndpointConnection' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubPrivateEndpointConnection' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubPrivateEndpointConnection' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubPrivateEndpointConnection' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Remove-AzEventHubPrivateEndpointConnection' has been removed.
The parameter set 'PrivateEndpointResourceIdParameterSet' for cmdlet 'Remove-AzEventHubPrivateEndpointConnection' has been removed.

### `Get-AzEventHubCluster`
The cmdlet 'Get-AzEventHubCluster' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes'.
The cmdlet 'Get-AzEventHubCluster' no longer supports the alias 'EventHubName' for parameter 'Name'.
The cmdlet 'Get-AzEventHubCluster' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubCluster' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubCluster' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzEventHubCluster' has been removed.

### `Set-AzEventHubGeoDRConfigurationBreakPair`
The parameter set 'GeoDRParameterSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' is no longer the default parameter set.
The parameter set 'GeoDRParameterSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' is no longer the default parameter set.
The cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' no longer supports the parameter 'PassThru' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRParameterSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' has been removed.
The parameter set 'GeoDRConfigurationInputObjectSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' has been removed.
The parameter set 'GeoDRConfigResourceIdParameterSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzEventHubGeoDRConfigurationBreakPair' has been removed.

### `Remove-AzEventHubConsumerGroup`
The parameter set 'ConsumergroupPropertiesSet' for cmdlet 'Remove-AzEventHubConsumerGroup' is no longer the default parameter set.
The parameter set 'ConsumergroupPropertiesSet' for cmdlet 'Remove-AzEventHubConsumerGroup' is no longer the default parameter set.
The parameter set 'ConsumergroupPropertiesSet' for cmdlet 'Remove-AzEventHubConsumerGroup' is no longer the default parameter set.
The cmdlet 'Remove-AzEventHubConsumerGroup' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubConsumerGroup' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubConsumerGroup' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSConsumerGroupAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzEventHubConsumerGroup' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubConsumerGroup' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubConsumerGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubConsumerGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubConsumerGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ConsumergroupPropertiesSet' for cmdlet 'Remove-AzEventHubConsumerGroup' has been removed.
The parameter set 'ConsumergroupInputObjectSet' for cmdlet 'Remove-AzEventHubConsumerGroup' has been removed.
The parameter set 'ConsumergroupResourceIdParameterSet' for cmdlet 'Remove-AzEventHubConsumerGroup' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzEventHubConsumerGroup' has been removed.

### `Approve-AzEventHubPrivateEndpointConnection`
The cmdlet 'Approve-AzEventHubPrivateEndpointConnection' no longer implements SupportsShouldProcess.
The cmdlet 'Approve-AzEventHubPrivateEndpointConnection' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubPrivateEndpointConnectionAttributes'.
The cmdlet 'Approve-AzEventHubPrivateEndpointConnection' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Approve-AzEventHubPrivateEndpointConnection' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Approve-AzEventHubPrivateEndpointConnection' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Approve-AzEventHubPrivateEndpointConnection' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Approve-AzEventHubPrivateEndpointConnection' has been removed.
The parameter set 'PrivateEndpointResourceIdParameterSet' for cmdlet 'Approve-AzEventHubPrivateEndpointConnection' has been removed.

### `Deny-AzEventHubPrivateEndpointConnection`
The cmdlet 'Deny-AzEventHubPrivateEndpointConnection' no longer implements SupportsShouldProcess.
The cmdlet 'Deny-AzEventHubPrivateEndpointConnection' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubPrivateEndpointConnectionAttributes'.
The cmdlet 'Deny-AzEventHubPrivateEndpointConnection' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Deny-AzEventHubPrivateEndpointConnection' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Deny-AzEventHubPrivateEndpointConnection' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Deny-AzEventHubPrivateEndpointConnection' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Deny-AzEventHubPrivateEndpointConnection' has been removed.
The parameter set 'PrivateEndpointResourceIdParameterSet' for cmdlet 'Deny-AzEventHubPrivateEndpointConnection' has been removed.

### `New-AzEventHubAuthorizationRule`
The cmdlet 'New-AzEventHubAuthorizationRule' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSSharedAccessAuthorizationRuleAttributes'.
The cmdlet 'New-AzEventHubAuthorizationRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubAuthorizationRule' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The element type for parameter 'Rights' has been changed from 'System.String' to 'Microsoft.Azure.PowerShell.Cmdlets.EventHub.Support.AccessRights'.
The cmdlet 'New-AzEventHubAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubAuthorizationRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubAuthorizationRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHubAuthorizationRule' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'New-AzEventHubAuthorizationRule' has been removed.
The parameter set 'EventhubAuthorizationRuleSet' for cmdlet 'New-AzEventHubAuthorizationRule' has been removed.

### `Set-AzEventHubAuthorizationRule`
The cmdlet 'Set-AzEventHubAuthorizationRule' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSSharedAccessAuthorizationRuleAttributes'.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Set-AzEventHubAuthorizationRule' is no longer the default parameter set.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Set-AzEventHubAuthorizationRule' is no longer the default parameter set.
The cmdlet 'Set-AzEventHubAuthorizationRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubAuthorizationRule' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSSharedAccessAuthorizationRuleAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzEventHubAuthorizationRule' no longer supports the alias 'AuthRuleObj' for parameter 'InputObject'.
The element type for parameter 'Rights' has been changed from 'System.String' to 'Microsoft.Azure.PowerShell.Cmdlets.EventHub.Support.AccessRights'.
The cmdlet 'Set-AzEventHubAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubAuthorizationRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubAuthorizationRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzEventHubAuthorizationRule' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Set-AzEventHubAuthorizationRule' has been removed.
The parameter set 'EventhubAuthorizationRuleSet' for cmdlet 'Set-AzEventHubAuthorizationRule' has been removed.
The parameter set 'AuthoRuleInputObjectSet' for cmdlet 'Set-AzEventHubAuthorizationRule' has been removed.

### `Remove-AzEventHubCluster`
The cmdlet 'Remove-AzEventHubCluster' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzEventHubCluster' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubCluster' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubCluster' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubCluster' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ClusterPropertiesSet' for cmdlet 'Remove-AzEventHubCluster' has been removed.
The parameter set 'ClusterInputObjectSet' for cmdlet 'Remove-AzEventHubCluster' has been removed.
The parameter set 'ClusterResourceIdParameterSet' for cmdlet 'Remove-AzEventHubCluster' has been removed.

### `Get-AzEventHubApplicationGroup`
The cmdlet 'Get-AzEventHubApplicationGroup' no longer implements SupportsShouldProcess.
The cmdlet 'Get-AzEventHubApplicationGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes'.
The parameter set 'ApplicationGroupPropertiesParameterSet' for cmdlet 'Get-AzEventHubApplicationGroup' is no longer the default parameter set.
The cmdlet 'Get-AzEventHubApplicationGroup' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubApplicationGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubApplicationGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubApplicationGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ApplicationGroupPropertiesParameterSet' for cmdlet 'Get-AzEventHubApplicationGroup' has been removed.
The parameter set 'ApplicationGroupResourceIdParameterSet' for cmdlet 'Get-AzEventHubApplicationGroup' has been removed.

### `Get-AzEventHub`
The cmdlet 'Get-AzEventHub' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes'.
The parameter set 'EventhubPropertiesSet' for cmdlet 'Get-AzEventHub' is no longer the default parameter set.
The parameter set 'EventhubPropertiesSet' for cmdlet 'Get-AzEventHub' is no longer the default parameter set.
The parameter set 'EventhubPropertiesSet' for cmdlet 'Get-AzEventHub' is no longer the default parameter set.
The cmdlet 'Get-AzEventHub' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHub' no longer supports the parameter 'MaxCount' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHub' no longer supports the parameter 'NamespaceObject' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHub' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHub' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHub' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'EventhubPropertiesSet' for cmdlet 'Get-AzEventHub' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'Get-AzEventHub' has been removed.

### `Remove-AzEventHub`
The parameter set 'EventhubDefaultSet' for cmdlet 'Remove-AzEventHub' is no longer the default parameter set.
The parameter set 'EventhubDefaultSet' for cmdlet 'Remove-AzEventHub' is no longer the default parameter set.
The cmdlet 'Remove-AzEventHub' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHub' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzEventHub' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHub' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHub' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHub' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHub' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'EventhubDefaultSet' for cmdlet 'Remove-AzEventHub' has been removed.
The parameter set 'EventhubInputObjectSet' for cmdlet 'Remove-AzEventHub' has been removed.
The parameter set 'EventhubResourceIdParameterSet' for cmdlet 'Remove-AzEventHub' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzEventHub' has been removed.

### `Set-AzEventHubApplicationGroup`
The cmdlet 'Set-AzEventHubApplicationGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes'.
The parameter set 'ApplicationGroupPropertiesParameterSet' for cmdlet 'Set-AzEventHubApplicationGroup' is no longer the default parameter set.
The cmdlet 'Set-AzEventHubApplicationGroup' no longer supports the parameter 'ThrottlingPolicyConfig' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubApplicationGroup' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubApplicationGroup' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzEventHubApplicationGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubApplicationGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubApplicationGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ApplicationGroupPropertiesParameterSet' for cmdlet 'Set-AzEventHubApplicationGroup' has been removed.
The parameter set 'ApplicationGroupResourceIdParameterSet' for cmdlet 'Set-AzEventHubApplicationGroup' has been removed.
The parameter set 'ApplicationGroupInputObjectParameterSet' for cmdlet 'Set-AzEventHubApplicationGroup' has been removed.

### `Get-AzEventHubConsumerGroup`
The cmdlet 'Get-AzEventHubConsumerGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSConsumerGroupAttributes'.
The cmdlet 'Get-AzEventHubConsumerGroup' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubConsumerGroup' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubConsumerGroup' no longer supports the parameter 'MaxCount' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubConsumerGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubConsumerGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubConsumerGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzEventHubConsumerGroup' has been removed.

### `New-AzEventHubSchemaGroup`
The cmdlet 'New-AzEventHubSchemaGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes'.
The cmdlet 'New-AzEventHubSchemaGroup' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubSchemaGroup' no longer supports the type 'System.String' for parameter 'SchemaCompatibility'.
The cmdlet 'New-AzEventHubSchemaGroup' no longer supports the type 'System.String' for parameter 'SchemaType'.
The cmdlet 'New-AzEventHubSchemaGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubSchemaGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubSchemaGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHubSchemaGroup' has been removed.

### `Remove-AzEventHubApplicationGroup`
The cmdlet 'Remove-AzEventHubApplicationGroup' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubApplicationGroup' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzEventHubApplicationGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubApplicationGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubApplicationGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ApplicationGroupPropertiesParameterSet' for cmdlet 'Remove-AzEventHubApplicationGroup' has been removed.
The parameter set 'ApplicationGroupResourceIdParameterSet' for cmdlet 'Remove-AzEventHubApplicationGroup' has been removed.
The parameter set 'ApplicationGroupInputObjectParameterSet' for cmdlet 'Remove-AzEventHubApplicationGroup' has been removed.

### `New-AzEventHubCluster`
The cmdlet 'New-AzEventHubCluster' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubClusterAttributes'.
The cmdlet 'New-AzEventHubCluster' no longer supports the type 'System.Nullable`1[System.Int32]' for parameter 'Capacity'.
The cmdlet 'New-AzEventHubCluster' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubCluster' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubCluster' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubCluster' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ClusterPropertiesSet' for cmdlet 'New-AzEventHubCluster' has been removed.
The parameter set 'ClusterResourceIdParameterSet' for cmdlet 'New-AzEventHubCluster' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHubCluster' has been removed.

### `Get-AzEventHubPrivateLink`
The cmdlet 'Get-AzEventHubPrivateLink' no longer implements SupportsShouldProcess.
The cmdlet 'Get-AzEventHubPrivateLink' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubPrivateLinkResourceAttributes'.
The cmdlet 'Get-AzEventHubPrivateLink' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubPrivateLink' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubPrivateLink' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateLinkPropertiesSet' for cmdlet 'Get-AzEventHubPrivateLink' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzEventHubPrivateLink' has been removed.

### `New-AzEventHubKey`
The cmdlet 'New-AzEventHubKey' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'New-AzEventHubKey' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubKey' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubKey' no longer supports the type 'System.String' for parameter 'RegenerateKey'.
The cmdlet 'New-AzEventHubKey' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubKey' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubKey' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHubKey' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'New-AzEventHubKey' has been removed.
The parameter set 'EventhubAuthorizationRuleSet' for cmdlet 'New-AzEventHubKey' has been removed.

### `New-AzEventHubThrottlingPolicyConfig`
The cmdlet 'New-AzEventHubThrottlingPolicyConfig' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubThrottlingPolicyConfigAttributes'.
The cmdlet 'New-AzEventHubThrottlingPolicyConfig' no longer supports the type 'System.String' for parameter 'MetricId'.
The cmdlet 'New-AzEventHubThrottlingPolicyConfig' no longer supports the parameter 'DefaultProfile' and no alias was found for the original parameter name.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHubThrottlingPolicyConfig' has been removed.

### `New-AzEventHubConsumerGroup`
The cmdlet 'New-AzEventHubConsumerGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSConsumerGroupAttributes'.
The cmdlet 'New-AzEventHubConsumerGroup' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubConsumerGroup' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubConsumerGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubConsumerGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubConsumerGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHubConsumerGroup' has been removed.

### `Set-AzEventHub`
The cmdlet 'Set-AzEventHub' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes'.
The cmdlet 'Set-AzEventHub' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHub' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzEventHub' no longer supports the alias 'EventHubObj' for parameter 'InputObject'.
The cmdlet 'Set-AzEventHub' no longer supports the parameter 'messageRetentionInDays' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHub' no longer supports the parameter 'partitionCount' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHub' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHub' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHub' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzEventHub' has been removed.
The parameter set 'EventhubInputObjectSet' for cmdlet 'Set-AzEventHub' has been removed.
The parameter set 'EventhubPropertiesSet' for cmdlet 'Set-AzEventHub' has been removed.

### `Get-AzEventHubSchemaGroup`
The cmdlet 'Get-AzEventHubSchemaGroup' no longer implements SupportsShouldProcess.
The cmdlet 'Get-AzEventHubSchemaGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes'.
The parameter set 'NamespaceSchemaGroupParameterSet' for cmdlet 'Get-AzEventHubSchemaGroup' is no longer the default parameter set.
The parameter set 'NamespaceSchemaGroupParameterSet' for cmdlet 'Get-AzEventHubSchemaGroup' is no longer the default parameter set.
The cmdlet 'Get-AzEventHubSchemaGroup' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubSchemaGroup' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubSchemaGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubSchemaGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubSchemaGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'NamespaceSchemaGroupParameterSet' for cmdlet 'Get-AzEventHubSchemaGroup' has been removed.
The parameter set 'SchemaGroupResourceIdParameterSet' for cmdlet 'Get-AzEventHubSchemaGroup' has been removed.

### `Get-AzEventHubPrivateEndpointConnection`
The cmdlet 'Get-AzEventHubPrivateEndpointConnection' no longer implements SupportsShouldProcess.
The cmdlet 'Get-AzEventHubPrivateEndpointConnection' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubPrivateEndpointConnectionAttributes'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Get-AzEventHubPrivateEndpointConnection' is no longer the default parameter set.
The cmdlet 'Get-AzEventHubPrivateEndpointConnection' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubPrivateEndpointConnection' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubPrivateEndpointConnection' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubPrivateEndpointConnection' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Get-AzEventHubPrivateEndpointConnection' has been removed.
The parameter set 'PrivateEndpointResourceIdParameterSet' for cmdlet 'Get-AzEventHubPrivateEndpointConnection' has been removed.

### `Set-AzEventHubCluster`
The cmdlet 'Set-AzEventHubCluster' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubClusterAttributes'.
The parameter set 'ClusterPropertiesSet' for cmdlet 'Set-AzEventHubCluster' is no longer the default parameter set.
The cmdlet 'Set-AzEventHubCluster' no longer supports the parameter 'Location' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubCluster' no longer supports the type 'System.Nullable`1[System.Int32]' for parameter 'Capacity'.
The cmdlet 'Set-AzEventHubCluster' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubClusterAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzEventHubCluster' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubCluster' no longer supports the type 'System.Collections.Hashtable' for parameter 'Tag'.
The cmdlet 'Set-AzEventHubCluster' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubCluster' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubCluster' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ClusterPropertiesSet' for cmdlet 'Set-AzEventHubCluster' has been removed.
The parameter set 'ClusterResourceIdParameterSet' for cmdlet 'Set-AzEventHubCluster' has been removed.
The parameter set 'ClusterInputObjectSet' for cmdlet 'Set-AzEventHubCluster' has been removed.

### `New-AzEventHub`
The cmdlet 'New-AzEventHub' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes'.
The cmdlet 'New-AzEventHub' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHub' no longer supports the parameter 'InputObject' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHub' no longer supports the type 'System.Nullable`1[System.Int64]' for parameter 'MessageRetentionInDays'.
The cmdlet 'New-AzEventHub' no longer supports the type 'System.Nullable`1[System.Int64]' for parameter 'PartitionCount'.
The cmdlet 'New-AzEventHub' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHub' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHub' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHub' has been removed.
The parameter set 'EventhubInputObjectSet' for cmdlet 'New-AzEventHub' has been removed.
The parameter set 'EventhubPropertiesSet' for cmdlet 'New-AzEventHub' has been removed.

### `New-AzEventHubApplicationGroup`
The cmdlet 'New-AzEventHubApplicationGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes'.
The cmdlet 'New-AzEventHubApplicationGroup' no longer supports the parameter 'ThrottlingPolicyConfig' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubApplicationGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubApplicationGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubApplicationGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ApplicationGroupPropertiesParameterSet' for cmdlet 'New-AzEventHubApplicationGroup' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHubApplicationGroup' has been removed.

### `Remove-AzEventHubGeoDRConfiguration`
The parameter set 'GeoDRParameterSet' for cmdlet 'Remove-AzEventHubGeoDRConfiguration' is no longer the default parameter set.
The parameter set 'GeoDRParameterSet' for cmdlet 'Remove-AzEventHubGeoDRConfiguration' is no longer the default parameter set.
The cmdlet 'Remove-AzEventHubGeoDRConfiguration' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzEventHubGeoDRConfiguration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubGeoDRConfiguration' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubGeoDRConfiguration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubGeoDRConfiguration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRParameterSet' for cmdlet 'Remove-AzEventHubGeoDRConfiguration' has been removed.
The parameter set 'GeoDRConfigurationInputObjectSet' for cmdlet 'Remove-AzEventHubGeoDRConfiguration' has been removed.
The parameter set 'GeoDRConfigResourceIdParameterSet' for cmdlet 'Remove-AzEventHubGeoDRConfiguration' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzEventHubGeoDRConfiguration' has been removed.

### `Test-AzEventHubName`
The cmdlet 'Test-AzEventHubName' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Test-AzEventHubName' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Test-AzEventHubName' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Test-AzEventHubName' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AliasCheckNameAvailabilitySet' for cmdlet 'Test-AzEventHubName' has been removed.
The parameter set 'NamespaceCheckNameAvailabilitySet' for cmdlet 'Test-AzEventHubName' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Test-AzEventHubName' has been removed.

### `Set-AzEventHubGeoDRConfigurationFailOver`
The parameter set 'GeoDRParameterSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' is no longer the default parameter set.
The parameter set 'GeoDRParameterSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' is no longer the default parameter set.
The cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' no longer supports the parameter 'PassThru' and no alias was found for the original parameter name.
The cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRParameterSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' has been removed.
The parameter set 'GeoDRConfigurationInputObjectSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' has been removed.
The parameter set 'GeoDRConfigResourceIdParameterSet' for cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzEventHubGeoDRConfigurationFailOver' has been removed.

### `New-AzEventHubGeoDRConfiguration`
The cmdlet 'New-AzEventHubGeoDRConfiguration' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes'.
The cmdlet 'New-AzEventHubGeoDRConfiguration' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubGeoDRConfiguration' no longer supports the parameter 'InputObject' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubGeoDRConfiguration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubGeoDRConfiguration' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'New-AzEventHubGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubGeoDRConfiguration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzEventHubGeoDRConfiguration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRParameterSet' for cmdlet 'New-AzEventHubGeoDRConfiguration' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'New-AzEventHubGeoDRConfiguration' has been removed.
The parameter set 'NamespaceResourceIdParameterSet' for cmdlet 'New-AzEventHubGeoDRConfiguration' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzEventHubGeoDRConfiguration' has been removed.

### `Remove-AzEventHubSchemaGroup`
The cmdlet 'Remove-AzEventHubSchemaGroup' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes'.
The parameter set 'NamespaceSchemaGroupParameterSet' for cmdlet 'Remove-AzEventHubSchemaGroup' is no longer the default parameter set.
The cmdlet 'Remove-AzEventHubSchemaGroup' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubSchemaGroup' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzEventHubSchemaGroup' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzEventHubSchemaGroup' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubSchemaGroup' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzEventHubSchemaGroup' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'NamespaceSchemaGroupParameterSet' for cmdlet 'Remove-AzEventHubSchemaGroup' has been removed.
The parameter set 'SchemaGroupInputObjectParameterSet' for cmdlet 'Remove-AzEventHubSchemaGroup' has been removed.
The parameter set 'SchemaGroupResourceIdParameterSet' for cmdlet 'Remove-AzEventHubSchemaGroup' has been removed.

### `Get-AzEventHubGeoDRConfiguration`
The cmdlet 'Get-AzEventHubGeoDRConfiguration' no longer has output type 'Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes'.
The parameter set 'GeoDRParameterSet' for cmdlet 'Get-AzEventHubGeoDRConfiguration' is no longer the default parameter set.
The parameter set 'GeoDRParameterSet' for cmdlet 'Get-AzEventHubGeoDRConfiguration' is no longer the default parameter set.
The cmdlet 'Get-AzEventHubGeoDRConfiguration' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes' for parameter 'InputObject'.
The cmdlet 'Get-AzEventHubGeoDRConfiguration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubGeoDRConfiguration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubGeoDRConfiguration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRParameterSet' for cmdlet 'Get-AzEventHubGeoDRConfiguration' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'Get-AzEventHubGeoDRConfiguration' has been removed.
The parameter set 'ResourceIdParameterSet' for cmdlet 'Get-AzEventHubGeoDRConfiguration' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzEventHubGeoDRConfiguration' has been removed.

### `Get-AzEventHubKey`
The cmdlet 'Get-AzEventHubKey' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubKey' no longer supports the parameter 'EventHub' and no alias was found for the original parameter name.
The cmdlet 'Get-AzEventHubKey' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubKey' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzEventHubKey' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzEventHubKey' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Get-AzEventHubKey' has been removed.
The parameter set 'EventhubAuthorizationRuleSet' for cmdlet 'Get-AzEventHubKey' has been removed.
The parameter set 'AliasAuthoRuleSet' for cmdlet 'Get-AzEventHubKey' has been removed.

## Az.MarketplaceOrdering

### `Get-AzMarketplaceTerms`
The cmdlet 'Get-AzMarketplaceTerms' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzMarketplaceTerms' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzMarketplaceTerms' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzMarketplaceTerms' has been removed.

### `Set-AzMarketplaceTerms`
The parameter set 'AgreementAcceptParameterSet' for cmdlet 'Set-AzMarketplaceTerms' is no longer the default parameter set.
The cmdlet 'Set-AzMarketplaceTerms' no longer supports the type 'Microsoft.Azure.Commands.MarketplaceOrdering.Models.PSAgreementTerms' for parameter 'Terms'.
The cmdlet 'Set-AzMarketplaceTerms' no longer supports the parameter 'InputObject' and no alias was found for the original parameter name.
The cmdlet 'Set-AzMarketplaceTerms' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzMarketplaceTerms' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzMarketplaceTerms' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AgreementAcceptParameterSet' for cmdlet 'Set-AzMarketplaceTerms' has been removed.
The parameter set 'AgreementRejectParameterSet' for cmdlet 'Set-AzMarketplaceTerms' has been removed.
The parameter set 'InputObjectAcceptParameterSet' for cmdlet 'Set-AzMarketplaceTerms' has been removed.
The parameter set 'InputObjectRejectParameterSet' for cmdlet 'Set-AzMarketplaceTerms' has been removed.

## Az.Migrate

### `New-AzMigrateReplicationVaultSetting`
The cmdlet 'New-AzMigrateReplicationVaultSetting' has been removed and no alias was found for the original cmdlet name.

### `Get-AzMigrateReplicationVaultSetting`
The cmdlet 'Get-AzMigrateReplicationVaultSetting' has been removed and no alias was found for the original cmdlet name.

### `Get-AzMigrateReplicationProtectionIntent`
The cmdlet 'Get-AzMigrateReplicationProtectionIntent' has been removed and no alias was found for the original cmdlet name.

### `Get-AzMigrateSupportedOperatingSystem`
The cmdlet 'Get-AzMigrateSupportedOperatingSystem' has been removed and no alias was found for the original cmdlet name.

### `Get-AzMigrateReplicationEligibilityResult`
The cmdlet 'Get-AzMigrateReplicationEligibilityResult' has been removed and no alias was found for the original cmdlet name.

### `New-AzMigrateReplicationProtectionIntent`
The cmdlet 'New-AzMigrateReplicationProtectionIntent' has been removed and no alias was found for the original cmdlet name.

## Az.Monitor

### `Get-AzAutoscaleSetting`
The cmdlet 'Get-AzAutoscaleSetting' no longer has output type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSAutoscaleSetting'.
The cmdlet 'Get-AzAutoscaleSetting' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Get-AzAutoscaleSetting' no longer supports the parameter 'DetailedOutput' and no alias was found for the original parameter name.
The cmdlet 'Get-AzAutoscaleSetting' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzAutoscaleSetting' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzAutoscaleSetting' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GetAutoscaleSetting' for cmdlet 'Get-AzAutoscaleSetting' has been removed.

### `Get-AzSubscriptionDiagnosticSettingCategory`
The cmdlet 'Get-AzSubscriptionDiagnosticSettingCategory' has been removed and no alias was found for the original cmdlet name.

### `Remove-AzAutoscaleSetting`
The cmdlet 'Remove-AzAutoscaleSetting' no longer has output type 'Microsoft.Azure.AzureOperationResponse'.
The cmdlet 'Remove-AzAutoscaleSetting' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Remove-AzAutoscaleSetting' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzAutoscaleSetting' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzAutoscaleSetting' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'RemoveAutoscaleSetting' for cmdlet 'Remove-AzAutoscaleSetting' has been removed.

### `New-AzAutoscaleProfile`
The cmdlet 'New-AzAutoscaleProfile' has been removed and no alias was found for the original cmdlet name.

### `Remove-AzDiagnosticSetting`
The cmdlet 'Remove-AzDiagnosticSetting' no longer has output type 'Microsoft.Azure.AzureOperationResponse'.
The cmdlet 'Remove-AzDiagnosticSetting' no longer supports the alias 'TargetResourceId' for parameter 'ResourceId'.
The cmdlet 'Remove-AzDiagnosticSetting' no longer supports the parameter 'SubscriptionId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzDiagnosticSetting' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzDiagnosticSetting' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzDiagnosticSetting' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzDiagnosticSetting' has been removed.
The parameter set 'ResourceIdParameterSet' for cmdlet 'Remove-AzDiagnosticSetting' has been removed.
The parameter set 'SubscriptionIdParameterSet' for cmdlet 'Remove-AzDiagnosticSetting' has been removed.

### `New-AzDiagnosticSetting`
The cmdlet 'New-AzDiagnosticSetting' no longer has output type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSServiceDiagnosticSettings'.
The cmdlet 'New-AzDiagnosticSetting' no longer supports the parameter 'DedicatedLogAnalyticsDestinationType' and no alias was found for the original parameter name.
The cmdlet 'New-AzDiagnosticSetting' no longer supports the parameter 'Setting' and no alias was found for the original parameter name.
The cmdlet 'New-AzDiagnosticSetting' no longer supports the alias 'TargetResourceId' for parameter 'ResourceId'.
The cmdlet 'New-AzDiagnosticSetting' no longer supports the parameter 'SubscriptionId' and no alias was found for the original parameter name.
The cmdlet 'New-AzDiagnosticSetting' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzDiagnosticSetting' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzDiagnosticSetting' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzDiagnosticSetting' has been removed.
The parameter set 'ResourceIdParameterSet' for cmdlet 'New-AzDiagnosticSetting' has been removed.
The parameter set 'SubscriptionIdParameterSet' for cmdlet 'New-AzDiagnosticSetting' has been removed.

### `New-AzScheduledQueryRule`
The cmdlet 'New-AzScheduledQueryRule' no longer has output type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSScheduledQueryRuleResource'.
The cmdlet 'New-AzScheduledQueryRule' no longer supports the parameter 'Source' and no alias was found for the original parameter name.
The cmdlet 'New-AzScheduledQueryRule' no longer supports the parameter 'Schedule' and no alias was found for the original parameter name.
The cmdlet 'New-AzScheduledQueryRule' no longer supports the parameter 'Action' and no alias was found for the original parameter name.
The cmdlet 'New-AzScheduledQueryRule' no longer supports the type 'System.Boolean' for parameter 'Enabled'.
The cmdlet 'New-AzScheduledQueryRule' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'New-AzScheduledQueryRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzScheduledQueryRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzScheduledQueryRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzScheduledQueryRule' has been removed.

### `New-AzScheduledQueryRuleAznsActionGroup`
The cmdlet 'New-AzScheduledQueryRuleAznsActionGroup' has been removed and no alias was found for the original cmdlet name.

### `Set-AzScheduledQueryRule`
The cmdlet 'Set-AzScheduledQueryRule' has been removed and no alias was found for the original cmdlet name.

### `New-AzScheduledQueryRuleSource`
The cmdlet 'New-AzScheduledQueryRuleSource' has been removed and no alias was found for the original cmdlet name.

### `New-AzScheduledQueryRuleLogMetricTrigger`
The cmdlet 'New-AzScheduledQueryRuleLogMetricTrigger' has been removed and no alias was found for the original cmdlet name.

### `Enable-AzActivityLogAlert`
The cmdlet 'Enable-AzActivityLogAlert' has been removed and no alias was found for the original cmdlet name.

### `New-AzAutoscaleNotification`
The cmdlet 'New-AzAutoscaleNotification' has been removed and no alias was found for the original cmdlet name.

### `New-AzActionGroup`
The cmdlet 'New-AzActionGroup' has been removed and no alias was found for the original cmdlet name.

### `New-AzDiagnosticDetailSetting`
The cmdlet 'New-AzDiagnosticDetailSetting' has been removed and no alias was found for the original cmdlet name.

### `New-AzAutoscaleRule`
The cmdlet 'New-AzAutoscaleRule' has been removed and no alias was found for the original cmdlet name.

### `New-AzScheduledQueryRuleSchedule`
The cmdlet 'New-AzScheduledQueryRuleSchedule' has been removed and no alias was found for the original cmdlet name.

### `Remove-AzActivityLogAlert`
The cmdlet 'Remove-AzActivityLogAlert' no longer has output type 'Microsoft.Azure.AzureOperationResponse'.
The cmdlet 'Remove-AzActivityLogAlert' no longer supports the type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSActivityLogAlertResource' for parameter 'InputObject'.
The cmdlet 'Remove-AzActivityLogAlert' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzActivityLogAlert' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzActivityLogAlert' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzActivityLogAlert' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'RemoveByNameAndResourceGroup' for cmdlet 'Remove-AzActivityLogAlert' has been removed.
The parameter set 'RemoveByResourceId' for cmdlet 'Remove-AzActivityLogAlert' has been removed.

### `New-AzAutoscaleWebhook`
The cmdlet 'New-AzAutoscaleWebhook' has been removed and no alias was found for the original cmdlet name.

### `Remove-AzScheduledQueryRule`
The cmdlet 'Remove-AzScheduledQueryRule' no longer supports the type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSScheduledQueryRuleResource' for parameter 'InputObject'.
The cmdlet 'Remove-AzScheduledQueryRule' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzScheduledQueryRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzScheduledQueryRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzScheduledQueryRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ByResourceId' for cmdlet 'Remove-AzScheduledQueryRule' has been removed.

### `Disable-AzActivityLogAlert`
The cmdlet 'Disable-AzActivityLogAlert' has been removed and no alias was found for the original cmdlet name.

### `Set-AzDiagnosticSetting`
The cmdlet 'Set-AzDiagnosticSetting' has been removed and no alias was found for the original cmdlet name.

### `Get-AzScheduledQueryRule`
The cmdlet 'Get-AzScheduledQueryRule' no longer has output type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSScheduledQueryRuleResource'.
The parameter set 'BySubscriptionOrResourceGroup' for cmdlet 'Get-AzScheduledQueryRule' is no longer the default parameter set.
The cmdlet 'Get-AzScheduledQueryRule' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzScheduledQueryRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzScheduledQueryRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzScheduledQueryRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'BySubscriptionOrResourceGroup' for cmdlet 'Get-AzScheduledQueryRule' has been removed.
The parameter set 'ByResourceId' for cmdlet 'Get-AzScheduledQueryRule' has been removed.

### `Add-AzAutoscaleSetting`
The cmdlet 'Add-AzAutoscaleSetting' has been removed and no alias was found for the original cmdlet name.

### `Update-AzScheduledQueryRule`
The cmdlet 'Update-AzScheduledQueryRule' no longer has output type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSScheduledQueryRuleResource'.
The cmdlet 'Update-AzScheduledQueryRule' no longer supports the type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSScheduledQueryRuleResource' for parameter 'InputObject'.
The cmdlet 'Update-AzScheduledQueryRule' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzScheduledQueryRule' no longer supports the type 'System.Boolean' for parameter 'Enabled'.
The cmdlet 'Update-AzScheduledQueryRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzScheduledQueryRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzScheduledQueryRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ByResourceId' for cmdlet 'Update-AzScheduledQueryRule' has been removed.

### `Get-AzDiagnosticSetting`
The cmdlet 'Get-AzDiagnosticSetting' no longer has output type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSServiceDiagnosticSettings'.
The parameter set 'ResourceIdParameterSet' for cmdlet 'Get-AzDiagnosticSetting' is no longer the default parameter set.
The cmdlet 'Get-AzDiagnosticSetting' no longer supports the alias 'TargetResourceId' for parameter 'ResourceId'.
The cmdlet 'Get-AzDiagnosticSetting' no longer supports the parameter 'SubscriptionId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzDiagnosticSetting' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzDiagnosticSetting' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzDiagnosticSetting' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzDiagnosticSetting' has been removed.
The parameter set 'ResourceIdParameterSet' for cmdlet 'Get-AzDiagnosticSetting' has been removed.
The parameter set 'SubscriptionIdParameterSet' for cmdlet 'Get-AzDiagnosticSetting' has been removed.

### `Get-AzDiagnosticSettingCategory`
The cmdlet 'Get-AzDiagnosticSettingCategory' no longer has output type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSDiagnosticSettingCategory'.
The cmdlet 'Get-AzDiagnosticSettingCategory' no longer supports the parameter 'TargetResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzDiagnosticSettingCategory' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzDiagnosticSettingCategory' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzDiagnosticSettingCategory' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzDiagnosticSettingCategory' has been removed.

### `New-AzScheduledQueryRuleAlertingAction`
The cmdlet 'New-AzScheduledQueryRuleAlertingAction' has been removed and no alias was found for the original cmdlet name.

### `New-AzActivityLogAlertCondition`
The cmdlet 'New-AzActivityLogAlertCondition' has been removed and no alias was found for the original cmdlet name.

### `Set-AzActivityLogAlert`
The cmdlet 'Set-AzActivityLogAlert' has been removed and no alias was found for the original cmdlet name.

### `Get-AzActivityLogAlert`
The cmdlet 'Get-AzActivityLogAlert' no longer has output type 'Microsoft.Azure.Commands.Insights.OutputClasses.PSActivityLogAlertResource'.
The cmdlet 'Get-AzActivityLogAlert' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzActivityLogAlert' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzActivityLogAlert' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GetByNameAndResourceGroup' for cmdlet 'Get-AzActivityLogAlert' has been removed.
The parameter set 'GetByResourceGroup' for cmdlet 'Get-AzActivityLogAlert' has been removed.

### `New-AzScheduledQueryRuleTriggerCondition`
The cmdlet 'New-AzScheduledQueryRuleTriggerCondition' has been removed and no alias was found for the original cmdlet name.

## Az.Network

### `New-AzFirewall`
The property 'IdentifyTopFatFlow' of type 'Microsoft.Azure.Commands.Network.Models.PSAzureFirewall' has been removed.
The property 'publicIPAddresses' of type 'Microsoft.Azure.Commands.Network.Models.PSAzureFirewallHubIpAddresses' has been removed.
The cmdlet 'New-AzFirewall' no longer supports the parameter 'IdentifyTopFatFlow' and no alias was found for the original parameter name.
The parameter set '__AllParameterSets' for cmdlet 'New-AzFirewall' has been removed.
The parameter set 'OldIpConfigurationParameterValues' for cmdlet 'New-AzFirewall' has been removed.
The parameter set 'IpConfigurationParameterValues' for cmdlet 'New-AzFirewall' has been removed.

### `New-AzFirewallHubIpAddress`
The property 'publicIPAddresses' of type 'Microsoft.Azure.Commands.Network.Models.PSAzureFirewallHubIpAddresses' has been removed.

### `Set-AzFirewall`
The property 'IdentifyTopFatFlow' of type 'Microsoft.Azure.Commands.Network.Models.PSAzureFirewall' has been removed.
The property 'IdentifyTopFatFlow' of type 'Microsoft.Azure.Commands.Network.Models.PSAzureFirewall' has been removed.

### `New-AzNetworkManagerAddressPrefixItem`
A validate set has been added for parameter 'AddressPrefixType' for cmdlet 'New-AzNetworkManagerAddressPrefixItem'.

### `New-AzNetworkManagerSecurityAdminConfiguration`
The element type for parameter 'ApplyOnNetworkIntentPolicyBasedService' has been changed from 'System.String' to 'Microsoft.Azure.Commands.Network.NewAzNetworkManagerSecurityAdminConfigurationCommand+NetworkIntentPolicyBasedServiceType'.

### `New-AzNetworkManager`
The element type for parameter 'NetworkManagerScopeAccess' has been changed from 'System.String' to 'Microsoft.Azure.Commands.Network.NewAzNetworkManagerCommand+NetworkManagerScopeAccessType'.

### `Get-AzFirewall`
The property 'publicIPAddresses' of type 'Microsoft.Azure.Commands.Network.Models.PSAzureFirewallHubIpAddresses' has been removed.
The property 'IdentifyTopFatFlow' of type 'Microsoft.Azure.Commands.Network.Models.PSAzureFirewall' has been removed.
The property 'IdentifyTopFatFlow' of type 'Microsoft.Azure.Commands.Network.Models.PSAzureFirewall' has been removed.

### `New-AzNetworkManagerConnectivityConfiguration`
A validate set has been added for parameter 'ConnectivityTopology' for cmdlet 'New-AzNetworkManagerConnectivityConfiguration'.

### `Deploy-AzNetworkManagerCommit`
A validate set has been added for parameter 'CommitType' for cmdlet 'Deploy-AzNetworkManagerCommit'.

### `New-AzNetworkManagerConnectivityGroupItem`
A validate set has been added for parameter 'GroupConnectivity' for cmdlet 'New-AzNetworkManagerConnectivityGroupItem'.

### `New-AzNetworkManagerSecurityAdminRule`
A validate set has been added for parameter 'Protocol' for cmdlet 'New-AzNetworkManagerSecurityAdminRule'.
A validate set has been added for parameter 'Direction' for cmdlet 'New-AzNetworkManagerSecurityAdminRule'.
A validate set has been added for parameter 'Access' for cmdlet 'New-AzNetworkManagerSecurityAdminRule'.

## Az.RecoveryServices

### `Get-AzRecoveryServicesBackupContainer`
The cmdlet 'Get-AzRecoveryServicesBackupContainer' no longer supports the parameter 'Status' and no alias was found for the original parameter name.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzRecoveryServicesBackupContainer' has been removed.

## Az.SecurityInsights

### `Update-AzSentinelAlertRuleAction`
The cmdlet 'Update-AzSentinelAlertRuleAction' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse'.
The parameter set 'ActionId' for cmdlet 'Update-AzSentinelAlertRuleAction' is no longer the default parameter set.
The cmdlet 'Update-AzSentinelAlertRuleAction' no longer supports the parameter 'AlertRuleId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelAlertRuleAction' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse' for parameter 'InputObject'.
The cmdlet 'Update-AzSentinelAlertRuleAction' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelAlertRuleAction' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelAlertRuleAction' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelAlertRuleAction' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ActionId' for cmdlet 'Update-AzSentinelAlertRuleAction' has been removed.
The parameter set 'ResourceId' for cmdlet 'Update-AzSentinelAlertRuleAction' has been removed.

### `New-AzSentinelIncidentOwner`
The cmdlet 'New-AzSentinelIncidentOwner' has been removed and no alias was found for the original cmdlet name.

### `New-AzSentinelIncidentComment`
The cmdlet 'New-AzSentinelIncidentComment' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.IncidentComments.PSSentinelIncidentComment'.
The cmdlet 'New-AzSentinelIncidentComment' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelIncidentComment' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelIncidentComment' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzSentinelIncidentComment' has been removed.

### `Get-AzSentinelBookmark`
The cmdlet 'Get-AzSentinelBookmark' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Bookmarks.PSSentinelBookmark'.
The cmdlet 'Get-AzSentinelBookmark' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelBookmark' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelBookmark' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelBookmark' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'BookmarkId.' for cmdlet 'Get-AzSentinelBookmark' has been removed.
The parameter set 'ResourceId' for cmdlet 'Get-AzSentinelBookmark' has been removed.

### `Update-AzSentinelAlertRule`
The cmdlet 'Update-AzSentinelAlertRule' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule'.
The parameter set 'AlertRuleId' for cmdlet 'Update-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'AlertRuleId' for cmdlet 'Update-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'AlertRuleId' for cmdlet 'Update-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'AlertRuleId' for cmdlet 'Update-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'AlertRuleId' for cmdlet 'Update-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'AlertRuleId' for cmdlet 'Update-AzSentinelAlertRule' is no longer the default parameter set.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the parameter 'AlertRuleId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.String' for parameter 'ProductFilter'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'DisplayNamesExcludeFilter'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'DisplayNamesFilter'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'SeveritiesFilter'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the parameter 'SuppressionDisabled' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.Nullable`1[System.TimeSpan]' for parameter 'QueryFrequency'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.Nullable`1[System.TimeSpan]' for parameter 'QueryPeriod'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.String' for parameter 'Severity'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'Tactic'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'Microsoft.Azure.Management.SecurityInsights.Models.TriggerOperator' for parameter 'TriggerOperator'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'System.Nullable`1[System.Int32]' for parameter 'TriggerThreshold'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule' for parameter 'InputObject'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelAlertRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AlertRuleId' for cmdlet 'Update-AzSentinelAlertRule' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Update-AzSentinelAlertRule' has been removed.
The parameter set 'InputObject' for cmdlet 'Update-AzSentinelAlertRule' has been removed.
The parameter set 'ResourceId' for cmdlet 'Update-AzSentinelAlertRule' has been removed.

### `Get-AzSentinelIncidentComment`
The cmdlet 'Get-AzSentinelIncidentComment' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.IncidentComments.PSSentinelIncidentComment'.
The cmdlet 'Get-AzSentinelIncidentComment' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelIncidentComment' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelIncidentComment' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelIncidentComment' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ResourceId' for cmdlet 'Get-AzSentinelIncidentComment' has been removed.

### `Get-AzSentinelAlertRuleAction`
The cmdlet 'Get-AzSentinelAlertRuleAction' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse'.
The parameter set 'AlertRuleId' for cmdlet 'Get-AzSentinelAlertRuleAction' is no longer the default parameter set.
The cmdlet 'Get-AzSentinelAlertRuleAction' no longer supports the parameter 'AlertRuleId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelAlertRuleAction' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelAlertRuleAction' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelAlertRuleAction' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AlertRuleId' for cmdlet 'Get-AzSentinelAlertRuleAction' has been removed.
The parameter set 'ActionId' for cmdlet 'Get-AzSentinelAlertRuleAction' has been removed.

### `Remove-AzSentinelIncident`
The cmdlet 'Remove-AzSentinelIncident' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident' for parameter 'InputObject'.
The cmdlet 'Remove-AzSentinelIncident' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelIncident' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelIncident' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'IncidentId' for cmdlet 'Remove-AzSentinelIncident' has been removed.

### `New-AzSentinelBookmark`
The cmdlet 'New-AzSentinelBookmark' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Bookmarks.PSSentinelBookmark'.
The parameter set 'BookmarkId.' for cmdlet 'New-AzSentinelBookmark' is no longer the default parameter set.
The cmdlet 'New-AzSentinelBookmark' no longer supports the parameter 'IncidentInfo' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelBookmark' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'Label'.
The cmdlet 'New-AzSentinelBookmark' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelBookmark' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelBookmark' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'BookmarkId.' for cmdlet 'New-AzSentinelBookmark' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzSentinelBookmark' has been removed.

### `Remove-AzSentinelAlertRule`
The cmdlet 'Remove-AzSentinelAlertRule' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule'.
The parameter set 'AlertRuleId' for cmdlet 'Remove-AzSentinelAlertRule' is no longer the default parameter set.
The cmdlet 'Remove-AzSentinelAlertRule' no longer supports the parameter 'AlertRuleId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzSentinelAlertRule' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule' for parameter 'InputObject'.
The cmdlet 'Remove-AzSentinelAlertRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelAlertRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelAlertRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AlertRuleId' for cmdlet 'Remove-AzSentinelAlertRule' has been removed.

### `Remove-AzSentinelAlertRuleAction`
The cmdlet 'Remove-AzSentinelAlertRuleAction' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse'.
The parameter set 'ActionId' for cmdlet 'Remove-AzSentinelAlertRuleAction' is no longer the default parameter set.
The cmdlet 'Remove-AzSentinelAlertRuleAction' no longer supports the parameter 'AlertRuleId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzSentinelAlertRuleAction' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse' for parameter 'InputObject'.
The cmdlet 'Remove-AzSentinelAlertRuleAction' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelAlertRuleAction' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelAlertRuleAction' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ActionId' for cmdlet 'Remove-AzSentinelAlertRuleAction' has been removed.

### `Get-AzSentinelAlertRule`
The cmdlet 'Get-AzSentinelAlertRule' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule'.
The cmdlet 'Get-AzSentinelAlertRule' no longer supports the parameter 'AlertRuleId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelAlertRule' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelAlertRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelAlertRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelAlertRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AlertRuleId' for cmdlet 'Get-AzSentinelAlertRule' has been removed.
The parameter set 'ResourceId' for cmdlet 'Get-AzSentinelAlertRule' has been removed.

### `Update-AzSentinelDataConnector`
The cmdlet 'Update-AzSentinelDataConnector' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.DataConnectors.PSSentinelDataConnector'.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' is no longer the default parameter set.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' is no longer the default parameter set.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' is no longer the default parameter set.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' is no longer the default parameter set.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' is no longer the default parameter set.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' is no longer the default parameter set.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' is no longer the default parameter set.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' is no longer the default parameter set.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the parameter 'DataConnectorId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.DataConnectors.PSSentinelDataConnector' for parameter 'InputObject'.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the parameter 'AwsRoleArn' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the parameter 'Logs' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the parameter 'DiscoveryLogs' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the parameter 'Indicators' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelDataConnector' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'DataConnectorId' for cmdlet 'Update-AzSentinelDataConnector' has been removed.
The parameter set 'InputObject' for cmdlet 'Update-AzSentinelDataConnector' has been removed.
The parameter set 'ResourceId' for cmdlet 'Update-AzSentinelDataConnector' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Update-AzSentinelDataConnector' has been removed.

### `Remove-AzSentinelBookmark`
The cmdlet 'Remove-AzSentinelBookmark' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Bookmarks.PSSentinelBookmark'.
The cmdlet 'Remove-AzSentinelBookmark' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.Bookmarks.PSSentinelBookmark' for parameter 'InputObject'.
The cmdlet 'Remove-AzSentinelBookmark' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelBookmark' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelBookmark' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'BookmarkId.' for cmdlet 'Remove-AzSentinelBookmark' has been removed.

### `New-AzSentinelIncident`
The cmdlet 'New-AzSentinelIncident' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident'.
The parameter set 'IncidentId' for cmdlet 'New-AzSentinelIncident' is no longer the default parameter set.
The parameter set 'IncidentId' for cmdlet 'New-AzSentinelIncident' is no longer the default parameter set.
The cmdlet 'New-AzSentinelIncident' no longer supports the parameter 'Classificaton' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelIncident' no longer supports the type 'System.String' for parameter 'ClassificationReason'.
The cmdlet 'New-AzSentinelIncident' no longer supports the type 'System.Collections.Generic.IList`1[Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentLabel]' for parameter 'Label'.
The cmdlet 'New-AzSentinelIncident' no longer supports the parameter 'Owner' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelIncident' no longer supports the type 'System.String' for parameter 'Severity'.
The cmdlet 'New-AzSentinelIncident' no longer supports the type 'System.String' for parameter 'Status'.
The cmdlet 'New-AzSentinelIncident' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelIncident' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelIncident' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'IncidentId' for cmdlet 'New-AzSentinelIncident' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzSentinelIncident' has been removed.

### `New-AzSentinelAlertRuleAction`
The cmdlet 'New-AzSentinelAlertRuleAction' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse'.
The cmdlet 'New-AzSentinelAlertRuleAction' no longer supports the parameter 'AlertRuleId' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelAlertRuleAction' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelAlertRuleAction' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelAlertRuleAction' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ActionId' for cmdlet 'New-AzSentinelAlertRuleAction' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzSentinelAlertRuleAction' has been removed.

### `Get-AzSentinelIncident`
The cmdlet 'Get-AzSentinelIncident' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident'.
The parameter set 'WorkspaceScope' for cmdlet 'Get-AzSentinelIncident' is no longer the default parameter set.
The parameter set 'WorkspaceScope' for cmdlet 'Get-AzSentinelIncident' is no longer the default parameter set.
The cmdlet 'Get-AzSentinelIncident' no longer supports the parameter 'OrderBy' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelIncident' no longer supports the parameter 'Max' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelIncident' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelIncident' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelIncident' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelIncident' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'WorkspaceScope' for cmdlet 'Get-AzSentinelIncident' has been removed.
The parameter set 'IncidentId' for cmdlet 'Get-AzSentinelIncident' has been removed.
The parameter set 'ResourceId' for cmdlet 'Get-AzSentinelIncident' has been removed.

### `Remove-AzSentinelDataConnector`
The cmdlet 'Remove-AzSentinelDataConnector' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.DataConnectors.PSSentinelDataConnector'.
The cmdlet 'Remove-AzSentinelDataConnector' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.DataConnectors.PSSentinelDataConnector' for parameter 'InputObject'.
The cmdlet 'Remove-AzSentinelDataConnector' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelDataConnector' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzSentinelDataConnector' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'DataConnectorId' for cmdlet 'Remove-AzSentinelDataConnector' has been removed.

### `New-AzSentinelDataConnector`
The cmdlet 'New-AzSentinelDataConnector' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.DataConnectors.PSSentinelDataConnector'.
The parameter set 'AzureActiveDirectory' for cmdlet 'New-AzSentinelDataConnector' is no longer the default parameter set.
The parameter set 'AzureActiveDirectory' for cmdlet 'New-AzSentinelDataConnector' is no longer the default parameter set.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'DataConnectorId' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'AzureActiveDirectory' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'AzureAdvancedThreatProtection' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'AzureSecurityCenter' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'AmazonWebServicesCloudTrail' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'MicrosoftCloudAppSecurity' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'MicrosoftDefenderAdvancedThreatProtection' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'Office365' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'ThreatIntelligence' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'AwsRoleArn' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'Logs' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'DiscoveryLogs' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the parameter 'Indicators' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelDataConnector' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AzureActiveDirectory' for cmdlet 'New-AzSentinelDataConnector' has been removed.
The parameter set 'AzureAdvancedThreatProtection' for cmdlet 'New-AzSentinelDataConnector' has been removed.
The parameter set 'AzureSecurityCenter' for cmdlet 'New-AzSentinelDataConnector' has been removed.
The parameter set 'AmazonWebServicesCloudTrail' for cmdlet 'New-AzSentinelDataConnector' has been removed.
The parameter set 'MicrosoftCloudAppSecurity' for cmdlet 'New-AzSentinelDataConnector' has been removed.
The parameter set 'MicrosoftDefenderAdvancedThreatProtection' for cmdlet 'New-AzSentinelDataConnector' has been removed.
The parameter set 'Office365' for cmdlet 'New-AzSentinelDataConnector' has been removed.
The parameter set 'ThreatIntelligence' for cmdlet 'New-AzSentinelDataConnector' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzSentinelDataConnector' has been removed.

### `New-AzSentinelAlertRule`
The cmdlet 'New-AzSentinelAlertRule' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.AlertRules.PSSentinelAlertRule'.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' is no longer the default parameter set.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the parameter 'Scheduled' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the parameter 'MicrosoftSecurityIncidentCreation' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the parameter 'Fusion' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the parameter 'AlertRuleId' and no alias was found for the original parameter name.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.String' for parameter 'ProductFilter'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'DisplayNamesExcludeFilter'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'DisplayNamesFilter'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'SeveritiesFilter'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.Nullable`1[System.TimeSpan]' for parameter 'QueryFrequency'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.Nullable`1[System.TimeSpan]' for parameter 'QueryPeriod'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.String' for parameter 'Severity'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'Tactic'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'Microsoft.Azure.Management.SecurityInsights.Models.TriggerOperator' for parameter 'TriggerOperator'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'System.Nullable`1[System.Int32]' for parameter 'TriggerThreshold'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzSentinelAlertRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'FusionAlertRule' for cmdlet 'New-AzSentinelAlertRule' has been removed.
The parameter set 'MicrosoftSecurityIncidentCreationRule' for cmdlet 'New-AzSentinelAlertRule' has been removed.
The parameter set 'ScheduledAlertRule' for cmdlet 'New-AzSentinelAlertRule' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzSentinelAlertRule' has been removed.

### `Get-AzSentinelAlertRuleTemplate`
The cmdlet 'Get-AzSentinelAlertRuleTemplate' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.AlertRuleTemplates.PSSentinelAlertRuleTemplate'.
The cmdlet 'Get-AzSentinelAlertRuleTemplate' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelAlertRuleTemplate' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelAlertRuleTemplate' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelAlertRuleTemplate' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AlertRuleTemplateId' for cmdlet 'Get-AzSentinelAlertRuleTemplate' has been removed.
The parameter set 'ResourceId' for cmdlet 'Get-AzSentinelAlertRuleTemplate' has been removed.

### `Update-AzSentinelIncident`
The cmdlet 'Update-AzSentinelIncident' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident'.
The parameter set 'IncidentId' for cmdlet 'Update-AzSentinelIncident' is no longer the default parameter set.
The parameter set 'IncidentId' for cmdlet 'Update-AzSentinelIncident' is no longer the default parameter set.
The cmdlet 'Update-AzSentinelIncident' no longer supports the parameter 'IncidentID' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelIncident' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncident' for parameter 'InputObject'.
The cmdlet 'Update-AzSentinelIncident' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelIncident' no longer supports the type 'System.String' for parameter 'Classification'.
The cmdlet 'Update-AzSentinelIncident' no longer supports the type 'System.String' for parameter 'ClassificationReason'.
The cmdlet 'Update-AzSentinelIncident' no longer supports the type 'System.Collections.Generic.IList`1[Microsoft.Azure.Commands.SecurityInsights.Models.Incidents.PSSentinelIncidentLabel]' for parameter 'Label'.
The cmdlet 'Update-AzSentinelIncident' no longer supports the parameter 'Owner' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelIncident' no longer supports the type 'System.String' for parameter 'Severity'.
The cmdlet 'Update-AzSentinelIncident' no longer supports the type 'System.String' for parameter 'Status'.
The cmdlet 'Update-AzSentinelIncident' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelIncident' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelIncident' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'IncidentId' for cmdlet 'Update-AzSentinelIncident' has been removed.
The parameter set 'InputObject' for cmdlet 'Update-AzSentinelIncident' has been removed.
The parameter set 'ResourceId' for cmdlet 'Update-AzSentinelIncident' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Update-AzSentinelIncident' has been removed.

### `Get-AzSentinelDataConnector`
The cmdlet 'Get-AzSentinelDataConnector' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.DataConnectors.PSSentinelDataConnector'.
The cmdlet 'Get-AzSentinelDataConnector' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzSentinelDataConnector' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelDataConnector' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzSentinelDataConnector' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'ResourceId' for cmdlet 'Get-AzSentinelDataConnector' has been removed.

### `Update-AzSentinelBookmark`
The cmdlet 'Update-AzSentinelBookmark' no longer has output type 'Microsoft.Azure.Commands.SecurityInsights.Models.Bookmarks.PSSentinelBookmark'.
The parameter set 'BookmarkId.' for cmdlet 'Update-AzSentinelBookmark' is no longer the default parameter set.
The cmdlet 'Update-AzSentinelBookmark' no longer supports the type 'Microsoft.Azure.Commands.SecurityInsights.Models.Bookmarks.PSSentinelBookmark' for parameter 'InputObject'.
The cmdlet 'Update-AzSentinelBookmark' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelBookmark' no longer supports the parameter 'IncidentInfo' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSentinelBookmark' no longer supports the type 'System.Collections.Generic.IList`1[System.String]' for parameter 'Label'.
The cmdlet 'Update-AzSentinelBookmark' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelBookmark' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Update-AzSentinelBookmark' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'BookmarkId.' for cmdlet 'Update-AzSentinelBookmark' has been removed.
The parameter set 'InputObject' for cmdlet 'Update-AzSentinelBookmark' has been removed.
The parameter set 'ResourceId' for cmdlet 'Update-AzSentinelBookmark' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Update-AzSentinelBookmark' has been removed.

## Az.ServiceBus

### `Set-AzServiceBusGeoDRConfigurationBreakPair`
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' is no longer the default parameter set.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' is no longer the default parameter set.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' no longer supports the parameter 'PassThru' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' has been removed.
The parameter set 'GeoDRConfigurationInputObjectSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' has been removed.
The parameter set 'GeoDRConfigResourceIdParameterSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzServiceBusGeoDRConfigurationBreakPair' has been removed.

### `Remove-AzServiceBusGeoDRConfiguration`
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Remove-AzServiceBusGeoDRConfiguration' is no longer the default parameter set.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Remove-AzServiceBusGeoDRConfiguration' is no longer the default parameter set.
The cmdlet 'Remove-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusGeoDRConfiguration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusGeoDRConfiguration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Remove-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set 'GeoDRConfigurationInputObjectSet' for cmdlet 'Remove-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set 'GeoDRConfigResourceIdParameterSet' for cmdlet 'Remove-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzServiceBusGeoDRConfiguration' has been removed.

### `Set-AzServiceBusTopic`
The cmdlet 'Set-AzServiceBusTopic' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes'.
The cmdlet 'Set-AzServiceBusTopic' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Set-AzServiceBusTopic' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusTopic' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusTopic' no longer supports the alias 'TopicObj' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusTopic' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusTopic' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusTopic' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzServiceBusTopic' has been removed.

### `New-AzServiceBusTopic`
The cmdlet 'New-AzServiceBusTopic' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'EnablePartitioning'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.String' for parameter 'AutoDeleteOnIdle'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.String' for parameter 'DefaultMessageTimeToLive'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.String' for parameter 'DuplicateDetectionHistoryTimeWindow'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'EnableBatchedOperations'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'EnableExpress'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.Nullable`1[System.Int64]' for parameter 'MaxSizeInMegabytes'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'RequiresDuplicateDetection'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'SupportOrdering'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the parameter 'SizeInBytes' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusTopic' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusTopic' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzServiceBusTopic' has been removed.

### `Get-AzServiceBusTopic`
The cmdlet 'Get-AzServiceBusTopic' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes'.
The cmdlet 'Get-AzServiceBusTopic' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Get-AzServiceBusTopic' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusTopic' no longer supports the parameter 'MaxCount' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusTopic' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusTopic' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusTopic' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzServiceBusTopic' has been removed.

### `Remove-AzServiceBusQueue`
The parameter set 'QueuePropertiesSet' for cmdlet 'Remove-AzServiceBusQueue' is no longer the default parameter set.
The parameter set 'QueuePropertiesSet' for cmdlet 'Remove-AzServiceBusQueue' is no longer the default parameter set.
The cmdlet 'Remove-AzServiceBusQueue' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Remove-AzServiceBusQueue' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusQueue' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzServiceBusQueue' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusQueue' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusQueue' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusQueue' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusQueue' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'QueuePropertiesSet' for cmdlet 'Remove-AzServiceBusQueue' has been removed.
The parameter set 'QueueInputObjectSet' for cmdlet 'Remove-AzServiceBusQueue' has been removed.
The parameter set 'QueueResourceIdSet' for cmdlet 'Remove-AzServiceBusQueue' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzServiceBusQueue' has been removed.

### `Remove-AzServiceBusMigration`
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Remove-AzServiceBusMigration' is no longer the default parameter set.
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Remove-AzServiceBusMigration' is no longer the default parameter set.
The cmdlet 'Remove-AzServiceBusMigration' no longer supports the parameter 'Name' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzServiceBusMigration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusMigration' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusMigration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusMigration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Remove-AzServiceBusMigration' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'Remove-AzServiceBusMigration' has been removed.
The parameter set 'NamespaceResourceIdParameterSet' for cmdlet 'Remove-AzServiceBusMigration' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzServiceBusMigration' has been removed.

### `New-AzServiceBusRule`
The cmdlet 'New-AzServiceBusRule' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSRulesAttributes'.
The cmdlet 'New-AzServiceBusRule' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'New-AzServiceBusRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusRule' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusRule' no longer supports the parameter 'Subscription' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusRule' no longer supports the parameter 'RequiresPreprocessing' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzServiceBusRule' has been removed.
The parameter set 'RuleActionPropertiesSet' for cmdlet 'New-AzServiceBusRule' has been removed.

### `Approve-AzServiceBusPrivateEndpointConnection`
The cmdlet 'Approve-AzServiceBusPrivateEndpointConnection' no longer implements SupportsShouldProcess.
The cmdlet 'Approve-AzServiceBusPrivateEndpointConnection' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusPrivateEndpointConnectionAttributes'.
The cmdlet 'Approve-AzServiceBusPrivateEndpointConnection' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Approve-AzServiceBusPrivateEndpointConnection' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Approve-AzServiceBusPrivateEndpointConnection' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Approve-AzServiceBusPrivateEndpointConnection' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Approve-AzServiceBusPrivateEndpointConnection' has been removed.
The parameter set 'PrivateEndpointResourceIdParameterSet' for cmdlet 'Approve-AzServiceBusPrivateEndpointConnection' has been removed.

### `Stop-AzServiceBusMigration`
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Stop-AzServiceBusMigration' is no longer the default parameter set.
The cmdlet 'Stop-AzServiceBusMigration' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Stop-AzServiceBusMigration' no longer supports the parameter 'Name' and no alias was found for the original parameter name.
The cmdlet 'Stop-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Stop-AzServiceBusMigration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Stop-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Stop-AzServiceBusMigration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Stop-AzServiceBusMigration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Stop-AzServiceBusMigration' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'Stop-AzServiceBusMigration' has been removed.
The parameter set 'NamespaceResourceIdParameterSet' for cmdlet 'Stop-AzServiceBusMigration' has been removed.

### `Get-AzServiceBusMigration`
The cmdlet 'Get-AzServiceBusMigration' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusMigrationConfigurationAttributes'.
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Get-AzServiceBusMigration' is no longer the default parameter set.
The cmdlet 'Get-AzServiceBusMigration' no longer supports the parameter 'Name' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSNamespaceAttributes' for parameter 'InputObject'.
The cmdlet 'Get-AzServiceBusMigration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusMigration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusMigration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Get-AzServiceBusMigration' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'Get-AzServiceBusMigration' has been removed.
The parameter set 'ResourceIdParameterSet' for cmdlet 'Get-AzServiceBusMigration' has been removed.

### `Remove-AzServiceBusTopic`
The parameter set 'TopicPropertiesSet' for cmdlet 'Remove-AzServiceBusTopic' is no longer the default parameter set.
The parameter set 'TopicPropertiesSet' for cmdlet 'Remove-AzServiceBusTopic' is no longer the default parameter set.
The cmdlet 'Remove-AzServiceBusTopic' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Remove-AzServiceBusTopic' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusTopic' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzServiceBusTopic' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusTopic' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusTopic' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusTopic' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusTopic' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'TopicPropertiesSet' for cmdlet 'Remove-AzServiceBusTopic' has been removed.
The parameter set 'TopicInputObjectSet' for cmdlet 'Remove-AzServiceBusTopic' has been removed.
The parameter set 'TopicResourceIdSet' for cmdlet 'Remove-AzServiceBusTopic' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzServiceBusTopic' has been removed.

### `Set-AzServiceBusRule`
The cmdlet 'Set-AzServiceBusRule' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSRulesAttributes'.
The cmdlet 'Set-AzServiceBusRule' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Set-AzServiceBusRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusRule' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusRule' no longer supports the parameter 'Subscription' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusRule' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSRulesAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzServiceBusRule' has been removed.

### `Get-AzServiceBusKey`
The cmdlet 'Get-AzServiceBusKey' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusKey' no longer supports the parameter 'Queue' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusKey' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusKey' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusKey' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusKey' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzServiceBusKey' has been removed.
The parameter set 'QueueAuthorizationRuleSet' for cmdlet 'Get-AzServiceBusKey' has been removed.
The parameter set 'TopicAuthorizationRuleSet' for cmdlet 'Get-AzServiceBusKey' has been removed.
The parameter set 'AliasAuthoRuleSet' for cmdlet 'Get-AzServiceBusKey' has been removed.

### `Set-AzServiceBusGeoDRConfigurationFailOver`
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' is no longer the default parameter set.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' is no longer the default parameter set.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' no longer supports the parameter 'PassThru' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' has been removed.
The parameter set 'GeoDRConfigurationInputObjectSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' has been removed.
The parameter set 'GeoDRConfigResourceIdParameterSet' for cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzServiceBusGeoDRConfigurationFailOver' has been removed.

### `New-AzServiceBusKey`
The cmdlet 'New-AzServiceBusKey' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusKey' no longer supports the parameter 'Queue' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusKey' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusKey' no longer supports the type 'System.String' for parameter 'RegenerateKey'.
The cmdlet 'New-AzServiceBusKey' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusKey' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusKey' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzServiceBusKey' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'New-AzServiceBusKey' has been removed.
The parameter set 'QueueAuthorizationRuleSet' for cmdlet 'New-AzServiceBusKey' has been removed.
The parameter set 'TopicAuthorizationRuleSet' for cmdlet 'New-AzServiceBusKey' has been removed.

### `Remove-AzServiceBusSubscription`
The parameter set 'SubscriptionPropertiesSet' for cmdlet 'Remove-AzServiceBusSubscription' is no longer the default parameter set.
The parameter set 'SubscriptionPropertiesSet' for cmdlet 'Remove-AzServiceBusSubscription' is no longer the default parameter set.
The parameter set 'SubscriptionPropertiesSet' for cmdlet 'Remove-AzServiceBusSubscription' is no longer the default parameter set.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusSubscription' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'SubscriptionPropertiesSet' for cmdlet 'Remove-AzServiceBusSubscription' has been removed.
The parameter set 'SubscriptionInputObjectSet' for cmdlet 'Remove-AzServiceBusSubscription' has been removed.
The parameter set 'SubscriptionResourceIdSet' for cmdlet 'Remove-AzServiceBusSubscription' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzServiceBusSubscription' has been removed.

### `Get-AzServiceBusRule`
The cmdlet 'Get-AzServiceBusRule' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSRulesAttributes'.
The cmdlet 'Get-AzServiceBusRule' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Get-AzServiceBusRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusRule' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusRule' no longer supports the parameter 'Subscription' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusRule' no longer supports the parameter 'MaxCount' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzServiceBusRule' has been removed.

### `New-AzServiceBusQueue`
The cmdlet 'New-AzServiceBusQueue' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'EnablePartitioning'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.String' for parameter 'LockDuration'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.String' for parameter 'AutoDeleteOnIdle'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.String' for parameter 'DefaultMessageTimeToLive'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.String' for parameter 'DuplicateDetectionHistoryTimeWindow'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'DeadLetteringOnMessageExpiration'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'EnableExpress'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.Nullable`1[System.Int32]' for parameter 'MaxDeliveryCount'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.Nullable`1[System.Int64]' for parameter 'MaxSizeInMegabytes'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the parameter 'MessageCount' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'RequiresDuplicateDetection'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'RequiresSession'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the parameter 'SizeInBytes' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusQueue' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusQueue' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzServiceBusQueue' has been removed.

### `Set-AzServiceBusQueue`
The cmdlet 'Set-AzServiceBusQueue' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes'.
The cmdlet 'Set-AzServiceBusQueue' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Set-AzServiceBusQueue' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusQueue' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusQueue' no longer supports the alias 'QueueObj' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusQueue' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusQueue' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusQueue' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzServiceBusQueue' has been removed.

### `Get-AzServiceBusNetworkRuleSet`
The cmdlet 'Get-AzServiceBusNetworkRuleSet' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSNetworkRuleSetAttributes'.
The parameter set 'NetworkRuleSetPropertiesSet' for cmdlet 'Get-AzServiceBusNetworkRuleSet' is no longer the default parameter set.
The cmdlet 'Get-AzServiceBusNetworkRuleSet' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusNetworkRuleSet' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusNetworkRuleSet' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusNetworkRuleSet' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusNetworkRuleSet' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'NetworkRuleSetPropertiesSet' for cmdlet 'Get-AzServiceBusNetworkRuleSet' has been removed.
The parameter set 'NetworkRuleSetNamespacePropertiesSet' for cmdlet 'Get-AzServiceBusNetworkRuleSet' has been removed.
The parameter set 'NetworkRuleSetResourceIdParameterSet' for cmdlet 'Get-AzServiceBusNetworkRuleSet' has been removed.

### `Deny-AzServiceBusPrivateEndpointConnection`
The cmdlet 'Deny-AzServiceBusPrivateEndpointConnection' no longer implements SupportsShouldProcess.
The cmdlet 'Deny-AzServiceBusPrivateEndpointConnection' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusPrivateEndpointConnectionAttributes'.
The cmdlet 'Deny-AzServiceBusPrivateEndpointConnection' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Deny-AzServiceBusPrivateEndpointConnection' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Deny-AzServiceBusPrivateEndpointConnection' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Deny-AzServiceBusPrivateEndpointConnection' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Deny-AzServiceBusPrivateEndpointConnection' has been removed.
The parameter set 'PrivateEndpointResourceIdParameterSet' for cmdlet 'Deny-AzServiceBusPrivateEndpointConnection' has been removed.

### `Get-AzServiceBusPrivateEndpointConnection`
The cmdlet 'Get-AzServiceBusPrivateEndpointConnection' no longer implements SupportsShouldProcess.
The cmdlet 'Get-AzServiceBusPrivateEndpointConnection' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusPrivateEndpointConnectionAttributes'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Get-AzServiceBusPrivateEndpointConnection' is no longer the default parameter set.
The cmdlet 'Get-AzServiceBusPrivateEndpointConnection' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusPrivateEndpointConnection' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusPrivateEndpointConnection' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusPrivateEndpointConnection' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Get-AzServiceBusPrivateEndpointConnection' has been removed.
The parameter set 'PrivateEndpointResourceIdParameterSet' for cmdlet 'Get-AzServiceBusPrivateEndpointConnection' has been removed.

### `Set-AzServiceBusAuthorizationRule`
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes'.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Set-AzServiceBusAuthorizationRule' is no longer the default parameter set.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Set-AzServiceBusAuthorizationRule' is no longer the default parameter set.
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer supports the parameter 'Queue' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer supports the alias 'AuthRuleObj' for parameter 'InputObject'.
The element type for parameter 'Rights' has been changed from 'System.String' to 'Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Support.AccessRights'.
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusAuthorizationRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Set-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'QueueAuthorizationRuleSet' for cmdlet 'Set-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'TopicAuthorizationRuleSet' for cmdlet 'Set-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'AuthoRuleInputObjectSet' for cmdlet 'Set-AzServiceBusAuthorizationRule' has been removed.

### `Remove-AzServiceBusAuthorizationRule`
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzServiceBusAuthorizationRule' is no longer the default parameter set.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzServiceBusAuthorizationRule' is no longer the default parameter set.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzServiceBusAuthorizationRule' is no longer the default parameter set.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzServiceBusAuthorizationRule' is no longer the default parameter set.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the parameter 'Queue' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the alias 'AuthRuleObj' for parameter 'InputObject'.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the parameter 'Force' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the parameter 'PassThru' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusAuthorizationRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'Remove-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'QueueAuthorizationRuleSet' for cmdlet 'Remove-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'TopicAuthorizationRuleSet' for cmdlet 'Remove-AzServiceBusAuthorizationRule' has been removed.

### `Get-AzServiceBusSubscription`
The cmdlet 'Get-AzServiceBusSubscription' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes'.
The cmdlet 'Get-AzServiceBusSubscription' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Get-AzServiceBusSubscription' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusSubscription' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusSubscription' no longer supports the parameter 'MaxCount' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusSubscription' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusSubscription' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusSubscription' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzServiceBusSubscription' has been removed.

### `Start-AzServiceBusMigration`
The cmdlet 'Start-AzServiceBusMigration' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes'.
The cmdlet 'Start-AzServiceBusMigration' no longer supports the parameter 'Name' and no alias was found for the original parameter name.
The cmdlet 'Start-AzServiceBusMigration' no longer supports the parameter 'TargetNameSpace' and no alias was found for the original parameter name.
The cmdlet 'Start-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Start-AzServiceBusMigration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Start-AzServiceBusMigration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Start-AzServiceBusMigration' has been removed.

### `Test-AzServiceBusName`
The cmdlet 'Test-AzServiceBusName' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Test-AzServiceBusName' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Test-AzServiceBusName' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Test-AzServiceBusName' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Test-AzServiceBusName' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'AliasCheckNameAvailabilitySet' for cmdlet 'Test-AzServiceBusName' has been removed.
The parameter set 'NamespaceCheckNameAvailabilitySet' for cmdlet 'Test-AzServiceBusName' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Test-AzServiceBusName' has been removed.

### `Get-AzServiceBusQueue`
The cmdlet 'Get-AzServiceBusQueue' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes'.
The cmdlet 'Get-AzServiceBusQueue' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Get-AzServiceBusQueue' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusQueue' no longer supports the parameter 'MaxCount' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusQueue' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusQueue' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusQueue' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzServiceBusQueue' has been removed.

### `Get-AzServiceBusGeoDRConfiguration`
The cmdlet 'Get-AzServiceBusGeoDRConfiguration' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes'.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Get-AzServiceBusGeoDRConfiguration' is no longer the default parameter set.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Get-AzServiceBusGeoDRConfiguration' is no longer the default parameter set.
The cmdlet 'Get-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSNamespaceAttributes' for parameter 'InputObject'.
The cmdlet 'Get-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusGeoDRConfiguration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusGeoDRConfiguration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'Get-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'Get-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set 'ResourceIdParameterSet' for cmdlet 'Get-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzServiceBusGeoDRConfiguration' has been removed.

### `Remove-AzServiceBusRule`
The parameter set 'RulePropertiesSet' for cmdlet 'Remove-AzServiceBusRule' is no longer the default parameter set.
The parameter set 'RulePropertiesSet' for cmdlet 'Remove-AzServiceBusRule' is no longer the default parameter set.
The parameter set 'RulePropertiesSet' for cmdlet 'Remove-AzServiceBusRule' is no longer the default parameter set.
The parameter set 'RulePropertiesSet' for cmdlet 'Remove-AzServiceBusRule' is no longer the default parameter set.
The parameter set 'RulePropertiesSet' for cmdlet 'Remove-AzServiceBusRule' is no longer the default parameter set.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the parameter 'Subscription' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes' for parameter 'InputObject'.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the parameter 'Force' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'RulePropertiesSet' for cmdlet 'Remove-AzServiceBusRule' has been removed.
The parameter set 'RuleResourceIdSet' for cmdlet 'Remove-AzServiceBusRule' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Remove-AzServiceBusRule' has been removed.

### `New-AzServiceBusAuthorizationRule`
The cmdlet 'New-AzServiceBusAuthorizationRule' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes'.
The cmdlet 'New-AzServiceBusAuthorizationRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusAuthorizationRule' no longer supports the parameter 'Queue' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusAuthorizationRule' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The element type for parameter 'Rights' has been changed from 'System.String' to 'Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Support.AccessRights'.
The cmdlet 'New-AzServiceBusAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusAuthorizationRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusAuthorizationRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'NamespaceAuthorizationRuleSet' for cmdlet 'New-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'QueueAuthorizationRuleSet' for cmdlet 'New-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'TopicAuthorizationRuleSet' for cmdlet 'New-AzServiceBusAuthorizationRule' has been removed.

### `Complete-AzServiceBusMigration`
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Complete-AzServiceBusMigration' is no longer the default parameter set.
The cmdlet 'Complete-AzServiceBusMigration' no longer supports the parameter 'Name' and no alias was found for the original parameter name.
The cmdlet 'Complete-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes' for parameter 'InputObject'.
The cmdlet 'Complete-AzServiceBusMigration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Complete-AzServiceBusMigration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Complete-AzServiceBusMigration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Complete-AzServiceBusMigration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'MigrationConfigurationPropertiesSet' for cmdlet 'Complete-AzServiceBusMigration' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'Complete-AzServiceBusMigration' has been removed.
The parameter set 'NamespaceResourceIdParameterSet' for cmdlet 'Complete-AzServiceBusMigration' has been removed.

### `Set-AzServiceBusNetworkRuleSet`
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSNetworkRuleSetAttributes'.
The parameter set 'NetworkRuleSetPropertiesSet' for cmdlet 'Set-AzServiceBusNetworkRuleSet' is no longer the default parameter set.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the parameter 'Name' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the type 'System.String' for parameter 'DefaultAction'.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the type 'System.String' for parameter 'PublicNetworkAccess'.
The element type for parameter 'IPRule' has been changed from 'Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetIpRulesAttributes' to 'Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.INwRuleSetIPRules'.
The element type for parameter 'VirtualNetworkRule' has been changed from 'Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetVirtualNetworkRulesAttributes' to 'Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.INwRuleSetVirtualNetworkRules'.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the alias 'VirtualNteworkRule' for parameter 'VirtualNetworkRule'.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSNetworkRuleSetAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusNetworkRuleSet' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'NetworkRuleSetInputObjectSet' for cmdlet 'Set-AzServiceBusNetworkRuleSet' has been removed.
The parameter set 'NetworkRuleSetPropertiesSet' for cmdlet 'Set-AzServiceBusNetworkRuleSet' has been removed.
The parameter set 'NetworkRuleSetResourceIdParameterSet' for cmdlet 'Set-AzServiceBusNetworkRuleSet' has been removed.

### `New-AzServiceBusSubscription`
The cmdlet 'New-AzServiceBusSubscription' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the type 'System.String' for parameter 'AutoDeleteOnIdle'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the type 'System.String' for parameter 'DefaultMessageTimeToLive'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'DeadLetteringOnMessageExpiration'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the parameter 'DeadLetteringOnFilterEvaluationExceptions' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'EnableBatchedOperations'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the type 'System.String' for parameter 'LockDuration'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the type 'System.Nullable`1[System.Int32]' for parameter 'MaxDeliveryCount'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the type 'System.Nullable`1[System.Boolean]' for parameter 'RequiresSession'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusSubscription' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'New-AzServiceBusSubscription' has been removed.

### `Set-AzServiceBusSubscription`
The cmdlet 'Set-AzServiceBusSubscription' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes'.
The cmdlet 'Set-AzServiceBusSubscription' no longer supports the alias 'ResourceGroup' for parameter 'ResourceGroupName'.
The cmdlet 'Set-AzServiceBusSubscription' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusSubscription' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Set-AzServiceBusSubscription' no longer supports the type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusSubscription' no longer supports the alias 'SubscriptionObj' for parameter 'InputObject'.
The cmdlet 'Set-AzServiceBusSubscription' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusSubscription' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Set-AzServiceBusSubscription' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Set-AzServiceBusSubscription' has been removed.

### `Get-AzServiceBusPrivateLink`
The cmdlet 'Get-AzServiceBusPrivateLink' no longer implements SupportsShouldProcess.
The cmdlet 'Get-AzServiceBusPrivateLink' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusPrivateLinkResourceAttributes'.
The cmdlet 'Get-AzServiceBusPrivateLink' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusPrivateLink' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusPrivateLink' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateLinkPropertiesSet' for cmdlet 'Get-AzServiceBusPrivateLink' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzServiceBusPrivateLink' has been removed.

### `Get-AzServiceBusAuthorizationRule`
The cmdlet 'Get-AzServiceBusAuthorizationRule' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes'.
The cmdlet 'Get-AzServiceBusAuthorizationRule' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusAuthorizationRule' no longer supports the parameter 'Queue' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusAuthorizationRule' no longer supports the parameter 'Topic' and no alias was found for the original parameter name.
The cmdlet 'Get-AzServiceBusAuthorizationRule' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusAuthorizationRule' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Get-AzServiceBusAuthorizationRule' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set '__AllParameterSets' for cmdlet 'Get-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'QueueAuthorizationRuleSet' for cmdlet 'Get-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'TopicAuthorizationRuleSet' for cmdlet 'Get-AzServiceBusAuthorizationRule' has been removed.
The parameter set 'AliasAuthoRuleSet' for cmdlet 'Get-AzServiceBusAuthorizationRule' has been removed.

### `New-AzServiceBusGeoDRConfiguration`
The cmdlet 'New-AzServiceBusGeoDRConfiguration' no longer has output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes'.
The cmdlet 'New-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'Namespace' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'InputObject' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusGeoDRConfiguration' no longer supports the parameter 'AsJob' and no alias was found for the original parameter name.
The cmdlet 'New-AzServiceBusGeoDRConfiguration' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusGeoDRConfiguration' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'New-AzServiceBusGeoDRConfiguration' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'GeoDRPropertiesSet' for cmdlet 'New-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set 'NamespaceInputObjectSet' for cmdlet 'New-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set 'NamespaceResourceIdParameterSet' for cmdlet 'New-AzServiceBusGeoDRConfiguration' has been removed.
The parameter set '__AllParameterSets' for cmdlet 'New-AzServiceBusGeoDRConfiguration' has been removed.

### `Remove-AzServiceBusPrivateEndpointConnection`
The cmdlet 'Remove-AzServiceBusPrivateEndpointConnection' no longer supports the parameter 'ResourceId' and no alias was found for the original parameter name.
The cmdlet 'Remove-AzServiceBusPrivateEndpointConnection' no longer supports the type 'Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusPrivateEndpointConnection' no longer supports the alias 'AzContext' for parameter 'DefaultProfile'.
The cmdlet 'Remove-AzServiceBusPrivateEndpointConnection' no longer supports the alias 'AzureRmContext' for parameter 'DefaultProfile'.
The parameter set 'PrivateEndpointPropertiesSet' for cmdlet 'Remove-AzServiceBusPrivateEndpointConnection' has been removed.
The parameter set 'PrivateEndpointResourceIdParameterSet' for cmdlet 'Remove-AzServiceBusPrivateEndpointConnection' has been removed.

## Az.Sql

### `Update-AzSqlServerAdvancedThreatProtectionSetting`
The cmdlet 'Update-AzSqlServerAdvancedThreatProtectionSetting' no longer has output type 'Microsoft.Azure.Commands.Sql.ThreatDetection.Model.ServerThreatDetectionPolicyModel'.
The cmdlet 'Update-AzSqlServerAdvancedThreatProtectionSetting' no longer supports the parameter 'NotificationRecipientsEmails' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSqlServerAdvancedThreatProtectionSetting' no longer supports the parameter 'EmailAdmins' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSqlServerAdvancedThreatProtectionSetting' no longer supports the parameter 'ExcludedDetectionType' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSqlServerAdvancedThreatProtectionSetting' no longer supports the parameter 'StorageAccountName' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSqlServerAdvancedThreatProtectionSetting' no longer supports the parameter 'RetentionInDays' and no alias was found for the original parameter name.
The parameter set '__AllParameterSets' for cmdlet 'Update-AzSqlServerAdvancedThreatProtectionSetting' has been removed.

### `Get-AzSqlServerAdvancedThreatProtectionSetting`
The cmdlet 'Get-AzSqlServerAdvancedThreatProtectionSetting' no longer has output type 'Microsoft.Azure.Commands.Sql.ThreatDetection.Model.ServerThreatDetectionPolicyModel'.

### `Clear-AzSqlDatabaseAdvancedThreatProtectionSetting`
The cmdlet 'Clear-AzSqlDatabaseAdvancedThreatProtectionSetting' has been removed and no alias was found for the original cmdlet name.

### `Update-AzSqlDatabaseAdvancedThreatProtectionSetting`
The cmdlet 'Update-AzSqlDatabaseAdvancedThreatProtectionSetting' no longer has output type 'Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DatabaseThreatDetectionPolicyModel'.
The cmdlet 'Update-AzSqlDatabaseAdvancedThreatProtectionSetting' no longer supports the parameter 'NotificationRecipientsEmails' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSqlDatabaseAdvancedThreatProtectionSetting' no longer supports the parameter 'EmailAdmins' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSqlDatabaseAdvancedThreatProtectionSetting' no longer supports the parameter 'ExcludedDetectionType' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSqlDatabaseAdvancedThreatProtectionSetting' no longer supports the parameter 'StorageAccountName' and no alias was found for the original parameter name.
The cmdlet 'Update-AzSqlDatabaseAdvancedThreatProtectionSetting' no longer supports the parameter 'RetentionInDays' and no alias was found for the original parameter name.
The parameter set '__AllParameterSets' for cmdlet 'Update-AzSqlDatabaseAdvancedThreatProtectionSetting' has been removed.

### `Clear-AzSqlServerAdvancedThreatProtectionSetting`
The cmdlet 'Clear-AzSqlServerAdvancedThreatProtectionSetting' has been removed and no alias was found for the original cmdlet name.

### `Disable-AzSqlServerAdvancedDataSecurity`
The cmdlet 'Disable-AzSqlServerAdvancedDataSecurity' no longer supports the alias 'Disable-AzSqlServerAdvancedThreatProtection'.

### `Get-AzSqlDatabaseAdvancedThreatProtectionSetting`
The cmdlet 'Get-AzSqlDatabaseAdvancedThreatProtectionSetting' no longer has output type 'Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DatabaseThreatDetectionPolicyModel'.

### `Enable-AzSqlServerAdvancedDataSecurity`
The cmdlet 'Enable-AzSqlServerAdvancedDataSecurity' no longer supports the alias 'Enable-AzSqlServerAdvancedThreatProtection'.

## Az.Storage

### `Get-AzStorageFileCopyState`
The cmdlet 'Get-AzStorageFileCopyState' no longer has output type 'Microsoft.Azure.Storage.File.CopyState'.

## Az.Synapse

### `Get-AzSynapseLinkConnectionLinkTableStatus`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.

### `Remove-AzSynapseLinkConnection`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.

### `Update-AzSynapseLinkConnectionLandingZoneCredential`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.

### `Get-AzSynapseLinkConnectionLinkTable`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.

### `Stop-AzSynapseLinkConnection`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.

### `Set-AzSynapseLinkConnection`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.

### `Get-AzSynapseLinkConnection`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.

### `Start-AzSynapseLinkConnection`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.

### `Set-AzSynapseLinkConnectionLinkTable`
The type of property 'Properties' of type 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource' has changed from 'Azure.Analytics.Synapse.Artifacts.Models.LinkConnection' to 'Microsoft.Azure.Commands.Synapse.Models.PSLinkConnection'.
