---
title: Azure PowerShell Change Log | Microsoft Docs
description: This is a history of changes made to Azure PowerShell in the latest release.
services: azure
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.workload:
ms.date: 5/1/2018
---

# Release notes

This is a list of changes made to Azure PowerShell in this release.

---
## 6.2.0 - June 2018
#### AzureRM.Profile
* Fix issue where version 10.0.3 of Newtonsoft.Json wasn't being loaded on module import

#### AzureRM.Compute
* VMSS VM Update feature
    - Added 'Update-AzureRmVmssVM' and 'New-AzureRmVMDataDisk' cmdlets
    - Add VirtualMachineScaleSetVM parameter to 'Add-AzureRmVMDataDisk' cmdlet to support adding a data disk to Vmss VM.

#### AzureRM.DataFactoryV2
* Updated the ADF .Net SDK version to 0.8.0-preview containing following changes:
    - Added Configure factory repository operation
    - Updated QuickBooks LinkedService to expose consumerKey and consumerSecret properties
    - Updated Several model types from SecretBase to Object
    - Added Blob Events trigger

### AzureRM.KeyVault
* Update documentation with example output

### AzureRM.Network
* Enable Traffic Analytics parameters on Network Watcher cmdlets

#### AzureRM.Resources
* Fix issue with 'Properties' property of 'PSResource' object(s) returned from 'Get-AzureRmResource'

#### AzureRM.Scheduler
* Fix issue with update ServiceBusQueueJob not setting new Auth values

### AzureRM.Sql
* Updated the following cmdlets with optional LicenseType parameter
	- New-AzureRmSqlDatabase; Set-AzureRmSqlDatabase
	- New-AzureRmSqlElasticPool; Set-AzureRmSqlElasticPool
	- New-AzureRmSqlDatabaseCopy
	- New-AzureRmSqlDatabaseSecondary
	- Restore-AzureRmSqlDatabase

#### AzureRM.Websites
* 'New-AzureRMWebApp' is updated to use common algorithms from the Strategy library.

## 6.1.0 - May 2018
#### AzureRM.Profile
* Fix issue where running 'Clear-AzureRmContext' would keep an empty context with the name of the previous default context, which prevented the user from creating a new context with the old name

#### AzureRM.AnalysisServices
* Enable Gateway assocaite/disassociate operations on AS.

#### AzureRM.ApiManagement
* Added support for ApiVersions, ApiReleases and ApiRevisions
* Added suppport for ServiceFabric Backend
* Added support for Application Insights Logger
* Added support for recognizing 'Basic' sku as a valid sku of Api Management service
* Added support for installing Certificates issued by private CA as Root or CA
* Added support for accepting Custom SSL certificates via KeyVault and Multiple proxy hostnames
* Added support for MSI identity
* Added support for accepting Policies via Url
NOTE: The following cmdlets will be deprecated in future release
   - Import-AzureRmApiManagementHostnameCertificate
   - New-AzureRmApiManagementHostnameConfiguration
   - Set-AzureRmApiManagementHostnames
   - Update-AzureRmApiManagementDeployment

#### AzureRM.Batch
* Release new cmdlet Get-AzureBatchPoolNodeCounts
* Release new cmdlet Start-AzureBatchComputeNodeServiceLogUpload

#### AzureRM.Consumption
* Add new parameters Expand, ResourceGroup, InstanceName, InstanceId, Tags, and Top on Cmdlet Get-AzureRmConsumptionUsageDetail

#### AzureRM.DataLakeStore
* Fix example for Export-AzureRmDataLakeStoreChildItemProperties
* Fix null parameter exception for Recurse case in Set-AzureRmDataLakeStoreItemAclEntry 
* Fix the help files for Set-AzureRmDataLakeStoreItemAclEntry, Set-AzureRmDataLakeStoreItemAcl, Remove-AzureRmDataLakeStoreItemAclEntry 

#### AzureRM.Network
* Bump up Network SDK version from 18.0.0-preview to 19.0.0-preview
* Added cmdlet to create protocol configuration
    - New-AzureRmNetworkWatcherProtocolConfiguration
* Added cmdlet to add a new circuit connection to an existing express route circuit.
    - Add-AzureRmExpressRouteCircuitConnectionConfig
* Added cmdlet to remove a circuit connection from an existing express route circuit.
    - Remove-AzureRmExpressRouteCircuitConnectionConfig
* Added cmdlet to retrieve a circuit connection
    - Get-AzureRmExpressRouteCircuitConnectionConfig

#### AzureRM.ServiceFabric
* Fixed server authentication usage with generated certificates (Issue #5998)

#### AzureRM.Sql
* Updated Auditing cmdlets to allow removing AuditActions or AuditActionGroups
* Fixed issue with Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy when setting a new flexible retention policy where the command would fail with 'Configure long term retention policy with azure recovery service vault and policy is no longer supported. Please submit request with the new flexible retention policy'.
* Update all Azure Sql Database/ElasticPool Creation/Update related cmdlets to use the new Database API, which support Sku property for scale and tier-related properties.
* The updated cmdlets including: 
	- New-AzureRmSqlDatabase; Set-AzureRmSqlDatabase
	- New-AzureRmSqlElasticPool; Set-AzureRmSqlElasticPool
	- New-AzureRmSqlDatabaseCopy
	- New-AzureRmSqlDatabaseSecondary
	- Restore-AzureRmSqlDatabase

#### AzureRM.TrafficManager
* Update the parameters for 'Get-AzureRmTrafficManagerProfile' so that -ResourceGroupName parameter is required when using -Name parameter.