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
ms.date: 5/1/2018
---

# Release notes

This is a list of changes made to Azure PowerShell in this release.

---

## 6.0.0 - May 2018

### General
* Set minimum dependency of modules to PowerShell 5.0

### Azure.Storage
* Support  as Storage blob container name
	- New-AzureStorageBlobContainer
	- Remove-AzureStorageBlobContainer
	- Set-AzureStorageBlobContent
	- Get-AzureStorageBlobContent
* Fix the issue that some Storage cmdlets failure output not contain detail failure information

### AzureRM.ApiManagement
* Introduce multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.Automation
* Remove deprecated 'Tags' alias from cmdlets
    - 'Set-AzureRmAutomationRunbook'

### AzureRM.Batch
* Updated New-AzureBatchPool documentation to remove deprecated example

### AzureRM.Cdn
* Introduce multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.Compute
* 'New-AzureRmVm' and 'New-AzureRmVmss' support verbose output of parameters
* 'New-AzureRmVm' and 'New-AzureRmVmss' (simple parameter set) support assigning user defined and(or) system defined identities to the VM(s).
* VMSS Redeploy and PerformMaintenance feature
    -  Add new switch parameter -Redeploy and -PerformMaintenance to 'Set-AzureRmVmss' and 'Set-AzureRmVmssVM'
* Add DisableVMAgent switch parameter to 'Set-AzureRmVMOperatingSystem' cmdlet
* 'New-AzureRmVm' and 'New-AzureRmVmss' (simple parameter set) support a 'Win10' image.
* 'Repair-AzureRmVmssServiceFabricUpdateDomain' cmdlet is added.
* Introduce multiple breaking changes
    - Please refer to the migration guide for more details
* 'Set-AzureRmVmDiskEncryptionExtension' makes AAD parameters optional

### AzureRM.DataFactories
* Remove deprecated 'Tags' alias from cmdlets
    - New-AzureRmDataFactory

### AzureRM.DataFactoryV2
* Updated the ADF .Net SDK version to 0.7.0-preview containing following changes:
    - Added execution parameters and connection managers property on ExecuteSSISPackage Activity
    - Updated PostgreSql, MySql llinked service to use full connection string instead of server, database, schema, username and password
    - Removed the schema from DB2 linked service
    - Removed schema property from Teradata linked service
    - Added LinkedService, Dataset, CopySource for Responsys

### AzureRM.DataLakeAnalytics
* Remove deprecated 'Tags' alias from cmdlets
    - 'New-AzureRmDataLakeAnalyticsAccount'
    - 'Set-AzureRmDataLakeAnalyticsAccount'

### AzureRM.DataLakeStore
* Add new feature of recursive Acl Change to Remove-AzureRmDataLakeStoreItemAclEntry, Set-AzureRmDataLakeStoreItemAclEntry, Set-AzureRmDataLakeStoreItemAcl
* Add new cmdlet for retrieving the content summary under a directory
* Add new cmdlet for retrieving the disk usage and Acl dump
* Correct return type of Set-AzureRmDataLakeStoreItemAcl bool to IEnumerable<DataLakeStoreItemAce>
* Correct return type of Set-AzureRmDataLakeStoreItemAclEntry bool to IEnumerable<DataLakeStoreItemAce>
* Breaking changes in Export-AzureRmDataLakeStoreItem, Import-AzureRmDataLakeStoreItem, Remove-AzureRmDataLakeStoreItem

### AzureRM.Dns
* Introduce multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.EventHub
* Updated Help for cmdlets with missing examples

### AzureRM.Insights
* Introduced multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.IotHub
* Enable tags and Basic Sku to the IotHub

### AzureRM.KeyVault
* Breaking changes to support piping scenarios
* Added new cmdlets: Backup/Restore-AzureKeyVaultManagedStorageAccount, Backup/Restore-AzureKeyVaultCertificate, Undo-AzureKeyVaultManagedStorageSasDefinitionRemoval, and Undo-AzureKeyVaultManagedStorageAccountRemoval

### AzureRM.MachineLearning
* Remove deprecated 'Tags' alias from cmdlets
    - Update-AzureRmMlCommitmentPlan

### AzureRM.Media
* Remove deprecated 'Tags' alias from cmdlets
    - 'Set-AzureRmMediaService'

### AzureRM.Network
* Add support for DDoS protection plan resource
* Introduced multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.NotificationHubs
* Introduce multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.OperationalInsights
* Introduce multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.Profile
* Enable context autosave by default
* Add USGovernmentOperationalInsightsEndpoint and USGovernmentOperationalInsightsEndpointResourceId properties to Azure environment for US Gov.

### AzureRM.RecoveryServices.SiteRecovery
* Fixed Authentication Header in SiteRecovery scenarios

### AzureRM.RedisCache
* Introduced multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.Resources
* Remove obsolete parameter -AtScopeAndBelow from Get-AzureRmRoledefinition call
* Include assignments to deleted USers/Groups/ServicePrincipals in Get-AzureRmRoleAssignment result
* Add Tab completers for Scope and ResourceType
* Add convenience cmdlet for creating ServicePrincipals
* Merge Get- and Find- functionality in Get-AzureRmResource
* Add AD Cmdlets:
  - Remove-AzureRmADGroupMember
  - Get-AzureRmADGroup
  - New-AzureRmADGroup
  - Remove-AzureRmADGroup
  - Remove-AzureRmADUser
  - Update-AzureRmADApplication
  - Update-AzureRmADServicePrincipal
  - Update-AzureRmADUser

### AzureRM.ServiceFabric
* Update default Linux image version sku
  - NewAzureServiceFabricCluster.cs default UbuntuServer1604 Sku update

### AzureRM.Storage
* Introduced multiple breaking changes
    - Please refer to the migration guide for more information

### AzureRM.Websites
* Upgrade to latest version of the Websites SDK
* Added -AssignIdentity & -Httpsonly properties for Set-AzureRmWebApp and Set-AzureRmWebAppSlot
* Added two new cmdlets: Get-AzureRmWebAppSnapshots and Restore-AzureRmWebAppSnapshot
