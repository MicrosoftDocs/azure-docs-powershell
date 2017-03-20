---
title: Azure PowerShell Change Log | Microsoft Docs
description: This is a history of changes made to Azure PowerShell in the latest release.
services: azure
author: sdwheeler
manager: carmonm
ms.assetid: e2dec06a-4179-49e3-b6b1-b0f278956d11
ms.service:
ms.product: azure
ms.devlang: powershell
ms.topic: reference
ms.workload:
ms.date: 03/06/2017
ms.author: sewhee
---

# Release notes

This is a history of changes made to Azure PowerShell in the latest release. For a comprehensive
history of changes, see the [Change log](https://github.com/Azure/azure-powershell/blob/dev/ChangeLog.md)
on GitHub.

## 2017.02.22 - Version 3.6.0
* AnalysisServices
    * Added State property in additional to ProvisioningState
        - All the cmdlet returning AnalysisService would have a new property 'State' used outside of provisioing.
        - The 'State' is intended to check status outside of provisioning, while 'ProvisioningState' is intended to check status related to Provisioning.
        - ProvisioningState and State are same in service side at this moment, the service side would differenciate ProvisioningState and State in future
* CognitiveServices
    * Integrate with Cognitive Services Management SDK 0.2.1 to support more Cognitive Services API Types and SKUs.
    * Remove the validation against “Type” and “SkuName” of Cognitive Services Account, this will allow the script to support new APIs/SKUs without changes.
* Compute
    * Updated Set-AzureRmVMDscExtension cmdlet WmfVersion parameter to support "5.1"
    * Updated Set-AzureRmVMChefExtension cmdlet to add following new options :
      - Daemon: Configures the chef-client service for unattended execution. e.g. -Daemon 'none' or e.g. -Daemon 'service'."
      - Secret: The encryption key used to encrypt and decrypt the data bag item values.
      - SecretFile: The path to the file that contains the encryption key used to encrypt and decrypt the data bag item values.
    * Fix for Get-AzureRmVM: Get-AzureRmVM did not display anything when the output includes availability set property.
    * New cmdlets:
        - Update-AzureRmAvailabilitySet: can update an unmanaged availability set to a managed availability set.
        - Add-AzureRmVmssDataDisk, Remove-AzureRmVmssDataDisk
    * New parameter, SkipVmBackup, for cmdlet Set-AzureRmVMDiskEncryptionExtension to allow user to skip backup creation for Linux VMs
* DataFactories
    * Fixed Get-AzureRmDataFactoryActivityWindow so it works for named pipeline and activity
* DataLakeAnalytics
    * Add Firewall Rule support to Data Lake Analytics:
        - Add-AzureRMDataLakeAnalyticsFirewallRule
        - Get-AzureRMDataLakeAnalyticsFirewallRule
        - Set-AzureRMDataLakeAnalyticsFirewallRule
        - Remove-AzureRMDataLakeAnalyticsFirewallRule
        - Set-AzureRMDataLakeAnalyticsAccount supports enabling/disabling the firewall and allowing/blocking Azure originating IPs through the firewall
        - Warnings will be raised if updating firewall rules when the firewall is disabled
    * Fix Get-AzureRMDataLakeAnalyticsJob functionality:
        - Top now correctly returns the number of jobs specified. The default number of jobs to return is 500. The more jobs requested the longer the command will take.
    * Remove explicit restrictions on resource locations. If Data Lake Analytics is not supported in a region, we will surface an error from the service.
* DataLakeStore
    * Update Upload and Download commands to use the new and improved Upload/Download helpers in the new DataLake.Store clients. This also gives better diagnostic logging, if enabled.
    * Default thread counts for Upload and download are now computed on a best effort basis based on the data being uploaded or downloaded. This should allow for good performance without specifying a thread count.
    * Update to Set-AzureRMDataLakeStoreAccount to allow for enabling and disabling Azure originating IPs through the firewall
    * Add warnings to Add and Set-AzureRMDataLakeStoreFirewallRule and AzureRMDataLakeStoreTrustedIdProvider if they are disabled
    * Remove explicit restrictions on resource locations. If Data Lake Store is not supported in a region, we will surface an error from the service.
* EventHub
    * Future Breaking Change Notification: We've added a warning about removing property 'ResourceGroupName' from the returned NamespceAttributes from cmdlets New-AzureRmEventHubNamespace, Get-AzureRmEvnetHubNamespace and Set-AzureRmEvnetHubNamespace
* Insights
    * Allow users to unselect data sinks for Set-AzureRmDiagnosticSettings
* Network
    * Added support for network Watcher APIs
        - New-AzureRmNetworkWatcher
        - Get-AzureRmNetworkWatcher
        - Remove-AzureRmNetworkWatcher
        - New-AzureRmPacketCaptureFilterConfig
        - New-AzureRmNetworkWatcherPacketCapture
        - Get-AzureRmNetworkWatcherPacketCapture
        - Stop-AzureRmNetworkWatcherPacketCapture
        - Remove-AzureRmNetworkWatcherPacketCapture
        - Get-AzureRmNetworkWatcherFlowLogSatus
        - Get-AzureRmNetworkWatcherNextHop
        - Get-AzureRmNetworkWatcherSecurityGroupView
        - Get-AzureRmNetworkWatcherTopology
        - Get-AzureRmNetworkWatcherTroubleshootingResult
        - Set-AzureRmNetworkWatcherConfigFlowLog
        - Start-AzureRmNetworkWatcherResourceTroubleshooting
        - Test-AzureRmNetworkWatcherIPFlow
    * Add-AzureRmExpressRouteCircuitPeeringConfig
        - Added new param :-RouteFilter to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource
        - Added new param :-RouteFilterId to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource id
    * New-AzureRmExpressRouteCircuitPeeringConfig
        - Added new param :-RouteFilter to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource
        - Added new param :-RouteFilterId to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource id
    * Set-AzureRmExpressRouteCircuitPeeringConfig
        - Added new param :-RouteFilter to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource
        - Added new param :-RouteFilterId to associate the BGP with route filter to filter out BGP communities via Microsoft peering. This parameter is set by resource id
    * New cmdlets for selective service feature
        - Get-AzureRmRouteFilter
        - New-AzureRmRouteFilter
        - Set-AzureRmRouteFilter
        - Remove-AzureRmRouteFilter
        - Add-AzureRmRouteFilterRuleConfig
        - Get-AzureRmRouteFilterRuleConfigobject
        - New-AzureRmRouteFilterRuleConfig
        - Set-AzureRmRouteFilterRuleConfig
        - Remove-AzureRmRouteFilterRuleConfig
* Resources
    * Support policy parameters for New-AzureRmPolicyDefinition and New-AzureRmPolicyAssignment
        - Users can now use Parameter parameter with New-AzureRmPolicyDefinition. This accepts both JSON string and file path.
        - Users can now provide policy parameter values in New-AzureRmPolicyAssignment in a couple of ways, including JSON string, file path, PS object, and through PowerShell parameters.
* Scheduler
    * Fixed issue to properly encode HTTP jobs' callback Uri in Scheduler PowerShell cmdlet
* Sql
    * Adding new cmdlets for support for Azure SQL feature Transparent Data Encryption (TDE) with Bring Your Own Key (BYOK) Support
    	- TDE with BYOK support is a new feature in Azure SQL, which allows users to encrypt their database with a key from Azure Key Vault. This feature is currently in private preview.
    	- Get-AzureRmSqlServerKeyVaultKey : This cmdlet returns a list of Azure Key Vault keys added to a Sql Server.
    	- Add-AzureRmSqlServerKeyVaultKey : This cmdlet adds an Azure Key Vault key to a Sql Server.
    	- Remove-AzureRmSqlServerKeyVaultKey : This cmdlet removes an Azure Key Vault key from a Sql Server.
    	- Get-AzureRmSqlServerTransparentDataEncryptionProtector : This cmdlet returns the current encryption protector for a Sql Server.
    	- Set-AzureRmSqlServerTransparentDataEncryptionProtector : This cmdlet sets the encryption protector for a Sql Server. The encryption protector can be set to a key from Azure Key Vault or a key that is managed by Azure Sql.
    * New feature: Set--AzureRmSqlDatabaseAuditing  and Set-AzureRmSqlDatabaseServerAuditingPolicy supports setting secondary storage key for AuditType Blob
    * Bug fix: Remove-AzureRmSqlDatabaseAuditing should set the UseServerDefault value to disabled
    * Bug fix: Fixing an issue of selecting classic storage account when creating / updating Auditing or Threat Detection policies
    * Bug fix: Set-AzureRmSqlDatabaseAuditing and Set-AzureRmSqlDatabaseServerAuditingPolicy commands use the AuditType value that was previously defined in case it has not been configured by the user.
    * Bug fix: In case Blob Auditing is defined, Remove-AzureRmSqlDatabaseAuditing and Remove-AzureRmSqlDatabaseServerAuditingPolicy commands disable the Auditing settings.
    * Adding new cmdlets for support for Azure SQL feature AutoDR:
        -This is a new feature in Azure SQL that supports failover of multiple Azure Sql Databases to the partner server at the same time during disaster and allows automatic failover
        - Add-AzureRmSqlDatabaseToFailoverGroup add Azure Sql Databases into a Failover Group
        - Get-AzureRmSqlDatabaseFailoverGroup get the Failover Group entity
        - New-AzureRmSqlDatabaseFailoverGroup creates a new Failover Group
        - Remove-AzureRmSqlDatabaseFromFailoverGroup removes Azure Sql Databases from a Failover Group
        - Remove-AzureRmSqlDatabaseFailoverGroup Failover Group deletes the Failover Group
        - Set-AzureRmSqlDatabaseFailoverGroup set Azure Sql Database Failover Policy and Grace Period entities of the Failover Group
        - Switch-AzureRmSqlDatabaseFailoverGroup issues the failover operation with data loss or without data loss
* Storage
    * Upgrade Microsoft.Azure.Management.Storage to version 6.1.0-preview
    * Add File Encryption features support to resource mode storage account cmdlets
        - New-AzureRmStorageAccount
        - Set-AzureRmStorageAccount

* ServiceManagement
    * Updated Set-AzureVMDscExtension cmdlet WmfVersion parameter to support "5.1"

    * Updated Set-AzureVMChefExtension cmdlet to add following new options :
        - Daemon: Configures the chef-client service for unattended execution. e.g. -Daemon 'none' or e.g. -Daemon 'service'."
        - Secret: The encryption key used to encrypt and decrypt the data bag item values.
        - SecretFile: The path to the file that contains the encryption key used to encrypt and decrypt the data bag item values.
