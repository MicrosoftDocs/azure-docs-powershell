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
ms.date: 11/14/2017
---

# Release notes

This is a list of changes made to Azure PowerShell in this release.

## 2017.11.10 Version 5.0.1
* Fixed assembly loading issue that caused some cmdlets to fail when executing in the following modules:
    - AzureRM.ApiManagement
    - AzureRM.Backup
    - AzureRM.Batch
    - AzureRM.Compute
    - AzureRM.DataFactories
    - AzureRM.HDInsight
    - AzureRM.KeyVault
    - AzureRM.RecoveryServices
    - AzureRM.RecoveryServices.Backup
    - AzureRM.RecoveryServices.SiteRecovery
    - AzureRM.RedisCache
    - AzureRM.SiteRecovery
    - AzureRM.Sql
    - AzureRM.Storage
    - AzureRM.StreamAnalytics

## 2017.11.8 - Version 5.0.0
* NOTE: This is a breaking change release. Please see the migration guide (https://aka.ms/azps-migration-guide) for a full list of introduced breaking changes.
* All cmdlets in AzureRM now support online help
    - Run Get-Help with the -Online parameter to open the online help in your default Internet browser
* AnalysisServices
    * Fixed Synchronize-AzureAsInstance command to work with new AsAzure REST API for sync
* ApiManagement
    * Please see the migration guide for breaking changes made to ApiManagement this release
    * Updated Cmdlet Get-AzureRmApiManagementUser to fix issue https://github.com/Azure/azure-powershell/issues/4510
    * Updated Cmdlet New-AzureRmApiManagementApi to create Api with Empty Path https://github.com/Azure/azure-powershell/issues/4069
* ApplicationInsights
    * Add commands to get/create/remove applicaiton insights resource
        - Get-AzureRmApplicationInsights
        - New-AzureRmApplicationInsights
        - Remove-AzureRmApplicationInsights
    * Add commands to get/update pricing/daily cap of applicaiton insights resource
        - Get-AzureRmApplicationInsights -IncludeDailyCap
        - Set-AzureRmApplicationInsightsPricingPlan
        - Set-AzureRmApplicationInsightsDailyCap
    * Add commands to get/create/update/remove continuous export of applicaiton insights resource
    	- Get-AzureRmApplicationInsightsContinuousExport
    	- Set-AzureRmApplicationInsightsContinuousExport
    	- New-AzureRmApplicationInsightsContinuousExport
    	- Remove-AzureRmApplicationInsightsContinuousExport
    * Add commands to get/create/remove api keys of applicaiton insights resoruce
    	- Get-AzureRmApplicationInsightsApiKey
    	- New-AzureRmApplicationInsightsApiKey
    	- Remove-AzureRmApplicationInsightsApiKey
* AzureBatch
    * Added new parameters to `New-AzureRmBatchAccount`.
        - `PoolAllocationMode`: The allocation mode to use for creating pools in the Batch account. To create a Batch account which allocates pool nodes in the user's subscription, set this to `UserSubscription`.
        - `KeyVaultId`: The resource ID of the Azure key vault associated with the Batch account.
        - `KeyVaultUrl`: The URL of the Azure key vault associated with the Batch account.
    * Updated parameters to `New-AzureBatchTask`.
        - Removed the `RunElevated` switch. The `UserIdentity` parameter has been added to replace `RunElevated`, and the equivalent behavior can be achieved by constructing a `PSUserIdentity` as shown below:
            - $autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
            - $userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
        - Added the `AuthenticationTokenSettings` parameter. This parameter allows you to request the Batch service provide an authentication token to the task when it runs, avoiding the need to pass Batch account keys to the task in order to issue requests to the Batch service.
        - Added the `ContainerSettings` parameter.
            - This parameter allows you to request the Batch service run the task inside a container.
        - Added the `OutputFiles` parameter.
            - This parameter allows you to configure the task to upload files to Azure Storage after it has finished.
    * Updated parameters to `New-AzureBatchPool`.
        - Added the `UserAccounts` parameter.
            - This parameter defines user accounts created on each node in the pool.
        - Added `TargetLowPriorityComputeNodes` and renamed `TargetDedicated` to `TargetDedicatedComputeNodes`.
            - A `TargetDedicated` alias was created for the `TargetDedicatedComputeNodes` parameter.
        - Added the `NetworkConfiguration` parameter.
            - This parameter allows you to configure the pools network settings.
    * Updated parameters to `New-AzureBatchCertificate`.
        - The `Password` parameter is now a `SecureString`.
    * Updated parameters to `New-AzureBatchComputeNodeUser`.
        - The `Password` parameter is now a `SecureString`.
    * Updated parameters to `Set-AzureBatchComputeNodeUser`.
        - The `Password` parameter is now a `SecureString`.
    * Renamed the `Name` parameter to `Path` on `Get-AzureBatchNodeFile`, `Get-AzureBatchNodeFileContent`, and `Remove-AzureBatchNodeFile`.
        - A `Name` alias was created for the `Path` parameter.
    * Changes to objects
        - Please see the Batch change log for the full list
    * Added support for Azure Active Directory based authentication.
        - To use Azure Active Directory authentication, retrieve a `BatchAccountContext` object using the `Get-AzureRmBatchAccount` cmdlet, and supply this `BatchAccountContext` to the `-BatchContext` parameter of a Batch service cmdlet. Azure Active Directory authentication is mandatory for accounts with `PoolAllocationMode = UserSubscription`.
        - For existing accounts or for new accounts created with `PoolAllocationMode = BatchService`, you may continue to use shared key authentication by retrieving a `BatchAccountContext` object using the `Get-AzureRmBatchAccoutKeys` cmdlet.
* Compute
    * Azure Disk Encryption Extension Commands
        - New Parameter for 'Set-AzureRmVmDiskEncryptionExtension': '-EncryptFormatAll' encrypt formats data disks
        - New Parameters for 'Set-AzureRmVmDiskEncryptionExtension': '-ExtensionPublisherName' and '-ExtensionType' allow switching to other versions of the extension
        - New Parameters for 'Disable-AzureRmVmDiskEncryption': '-ExtensionPublisherName' and '-ExtensionType' allow switching to other versions of the extension
        - New Parameters for 'Get-AzureRmVmDiskEncryptionStatus': '-ExtensionPublisherName' and '-ExtensionType' allow switching to other versions of the extension
* DataLakeAnalytics
    * Please see the migration guide for breaking changes made to DataLakeAnalytics this release
    * Changed one of the two OutputTypes of Get-AzureRmDataLakeAnalyticsAccount
        - List\<DataLakeAnalyticsAccount> to List\<PSDataLakeAnalyticsAccountBasic>
        - The properties of PSDataLakeAnalyticsAccountBasic is a strict subset of the properties of DataLakeAnalyticsAccount
        - The additional properties that are in DataLakeAnalyticsAccount are not returned by the service.  Therefore, this change is to reflect this accurately. These additional properties are still in PSDataLakeAnalyticsAccountBasic, but they are tagged as Obsolete.
    * Changed one of the two OutputTypes of Get-AzureRmDataLakeAnalyticsJob
        - List\<JobInformation> to List\<PSJobInformationBasic>
        - The properties of PSJobInformationBasic is a strict subset of the properties of JobInformation
        - The additional properties that are in JobInformation are not returned by the service.  Therefore, this change is to reflect this accurately. These additional properties are still in PSJobInformationBasic, but they are tagged as Obsolete.
* DataLakeStore
    * Please see the migration guide for breaking changes made to DataLakeStore this release
    * Changed one of the two OutputTypes of Get-AzureRmDataLakeStoreAccount
        - List\<PSDataLakeStoreAccount> to List\<PSDataLakeStoreAccountBasic>
        - The properties of PSDataLakeStoreAccountBasic is a strict subset of the properties of PSDataLakeStoreAccount
        - The additional properties that are in PSDataLakeStoreAccount are not returned by the service.  Therefore, this change is to reflect this accurately. These additional properties are still in PSDataLakeStoreAccountBasic, but they are tagged as Obsolete.
* Dns
    * Support for CAA record types in Azure DNS
       - Supports all operations on CAA record type
* EventHub
    * Please see the migration guide for breaking changes made to EventHub this release
* Insights
    * Please see the migration guide for breaking changes made to Insights this release
* Network
    * Please see the migration guide for breaking changes made to Network this release
    * Added cmdlet to list available internet service providers for a specified Azure region
        - Get-AzureRmNetworkWatcherReachabilityProvidersList
    * Added cmdlet to get the relative latency score for internet service providers from a specified location to Azure regions
        - Get-AzureRmNetworkWatcherReachabilityReport
* Profile
    - Set-AzureRmDefault
        - Use this cmdlet to set a default resource group.  This will make the -ResourceGroup parameter optional for some cmdlets, and will use the default when a resource group is not specified
        - ```Set-AzureRmDefault -ResourceGroupName "ExampleResourceGroup"```
        - If resource group specified exists in the subscription, this resource group will be set to default.  Otherwise, the resource group will be created and then set to default.
    - Get-AzureRmDefault
        - Use this cmdlet to get the current default resource group (and other defaults in the future).
        - ```Get-AzureRmDefault -ResourceGroup```
    - Clear-AzureRmDefault
        - Use this cmdlet to remove the current default resource group
        - ```Clear-AzureRmDefault -ResourceGroup```
    - Add-AzureRmEnvironment and Set-AzureRmEnvironment
        - Add the BatchAudience parameter, which allows you to specify the Azure Batch Active Directory audience to use when acquiring authentication tokens for the Batch service.
* RecoveryServices.Backup
    * Added cmdlets to perform instant file recovery.
        - Get-AzureRmRecoveryServicesBackupRPMountScript
        - Disable-AzureRmRecoveryServicesBackupRPMountScript
    * Updated RecoveryServices.Backup SDK version to the latest
    * Updated tests for the Azure VM workload so that, all setups needed for test runs are done by the tests themselves.
    * Fixes https://github.com/Azure/azure-powershell/issues/3164
* RecoveryServices.SiteRecovery
    * Changes for ASR VMware to Azure Site Recovery (cmdlets are currently supporting operations for Enterprise to Enterprise, Enterprise to Azure, HyperV to Azure)
        - New-AzureRmRecoveryServicesAsrPolicy
        - New-AzureRmRecoveryServicesAsrProtectedItem
        - Update-AzureRmRecoveryServicesAsrPolicy
        - Update-AzureRmRecoveryServicesAsrProtectionDirection
    * Added support to AAD-based vault
    * Added cmdlets to manage VCenter resources
        - Get-AzureRmRecoveryServicesAsrVCenter
        - New-AzureRmRecoveryServicesAsrVCenter
        - Remove-AzureRmRecoveryServicesAsrVCenter
        - Update-AzureRmRecoveryServicesAsrVCenter
    * Added other cmdlets
        - Get-AzureRmRecoveryServicesAsrAlertSetting
        - Get-AzureRmRecoveryServicesAsrEvent
        - New-AzureRmRecoveryServicesAsrProtectableItem
        - Set-AzureRmRecoveryServicesAsrAlertSetting
        - Start-AzureRmRecoveryServicesAsrResynchronizeReplicationJob
        - Start-AzureRmRecoveryServicesAsrSwitchProcessServerJob
        - Start-AzureRmRecoveryServicesAsrTestFailoverCleanupJob
        - Update-AzureRmRecoveryServicesAsrMobilityService
* ServiceBus
    - Please see the migration guide for breaking changes made to ServiceBus this release
* Sql
    * Adding support for list and cancel the asynchronous updateslo operation on the database
    	- update existing cmdlet Get-AzureRmSqlDatabaseActivity to return DB updateslo operation status.
    	- add new cmdlet Stop-AzureRmSqlDatabaseActivity for cancel the asynchronous updateslo operation on the database.
    * Adding support for Zone Redundancy for databases and elastic pools
    	- Adding ZoneRedundant switch parameter to New-AzureRmSqlDatabase
    	- Adding ZoneRedundant switch parameter to Set-AzureRmSqlDatabase
    	- Adding ZoneRedundant switch parameter to New-AzureRmSqlElasticPool
    	- Adding ZoneRedundant switch parameter to Set-AzureRmSqlElasticPool
    * Adding support for Server DNS Aliases
    	- Adding Get-AzureRmSqlServerDnsAlias cmdlet which gets server dns aliases by server and alias name or a list of server dns aliases for an azure Sql Server.
    	- Adding New-AzureRmSqlServerDnsAlias cmdlet which creates new server dns alias for a given Azure Sql server
    	- Adding Set-AzurermSqlServerDnsAlias cmlet which allows updating a Azure Sql Server to which server dns alias is pointing
    	- Adding Remove-AzureRmSqlServerDnsAlias cmdlet which removes a server dns alias for a Azure Sql Server
* Azure.Storage
    * Upgrade to Azure Storage Client Library 8.5.0 and Azure Storage DataMovement Library 0.6.3
    * Add File Share Snapshot Support Feature
        - Add 'SnapshotTime' parameter to Get-AzureStorageShare
        - Add 'IncludeAllSnapshot' parameter to Remove-AzureStorageShare