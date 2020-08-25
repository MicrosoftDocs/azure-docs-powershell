---
title: Azure PowerShell Change Log
description: This is a history of changes made to Azure PowerShell in the latest release.
ms.devlang: powershell
ms.topic: conceptual
ms.workload:
ms.date: 2/20/2018
---
# Azure PowerShell Release notes

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

This is a list of changes made to Azure PowerShell in this release.

---

## Azure PowerShell 5.7.0

Azure PowerShell 5.7.0 Installer: [link](https://github.com/Azure/azure-powershell/releases/download/v5.7.0-April2018/azure-powershell.5.7.0.msi)

Gallery Module for ARM Cmdlets: [link](https://www.powershellgallery.com/packages/AzureRM/5.7.0)

To install `AzureRM` from the PowerShell Gallery, run the following command:

```powershell-interactive
Install-Module -Name AzureRM -Repository PSGallery -Force
```

To update from an older version of `AzureRM`, run the following command:

```powershell-interactive
Update-Module -Name AzureRM
```

### Changes Since Last Release

#### General
* Updated to the latest version of the Azure ClientRuntime

#### Azure.Storage
* Fix the issue that upload Blob and upload File cmdlets fail on FIPS policy enabled machines
	- Set-AzureStorageBlobContent
	- Set-AzureStorageFileContent

#### AzureRM.Billing
* New Cmdlet Get-AzureRmEnrollmentAccount
  - cmdlet to retrieve enrollment accounts

#### AzureRM.CognitiveServices
* Integrate with Cognitive Services Management SDK version 4.0.0.
* Add Get-AzureRmCognitiveServicesAccountUsage operation.

#### AzureRM.Compute
* `Get-AzureRmVmssDiskEncryptionStatus` supports encryption status at data disk level
* `Get-AzureRmVmssVmDiskEncryptionStatus` supports encryption status at data disk level
* Update for Zone Resilient
* 'New-AzureRmVm' and 'New-AzureRmVmss' (simple parameter set) support availability zones.

#### AzureRM.ContainerRegistry
* Decouple reliance on Commands.Resources.Rest and ARM/Storage SDKs.

#### AzureRM.DataLakeStore
* Add debug functionality
* Update the version of the ADLS dataplane SDK to 1.1.2
* Export-AzureRmDataLakeStoreItem - Deprecated parameters PerFileThreadCount, ConcurrentFileCount and introduced parameter Concurrency
* Import-AzureRMDataLakeStoreItem - Deprecated parametersPerFileThreadCount, ConcurrentFileCount and introduced parameter Concurrency
* Get-AzureRMDataLakeStoreItemContent - Fixed the tail behavior for contents greater than 4MB
* Set-AzureRMDataLakeStoreItemExpiry - Introduced new parameter set SetRelativeExpiry for setting relative expiration time
* Remove-AzureRmDataLakeStoreItem - Deprecated parameter Clean.

#### AzureRM.EventHub
* Fixed AlternameName in New-AzureRmEventHubGeoDRConfiguration

#### AzureRM.KeyVault
* Updated cmdlets to include piping scenarios
* Add deprecation messages for upcoming breaking change release

#### AzureRM.Network
* Fix error message with Network cmdlets

#### AzureRM.ServiceBus
* Added 'properties' in CorrelationFilter of Rules to support customproperties
* updated New-AzureRmServiceBusGeoDRConfiguration help and fixed Rules cmdlet output
* Fixed auto-forward properties in New-AzureRmServiceBusQueue and New-AzureRmServiceBusSubscription cmdlet

#### AzureRM.Sql
* Add new cmdlet 'Stop-AzureRmSqlElasticPoolActivity' to support canceling the asynchronous operations on elastic pool
* Update the response for cmdlets Get-AzureRmSqlDatabaseActivity and Get-AzureRmSqlElasticPoolActivity to reflect more information in the response

Changes since last release: https://github.com/Azure/azure-powershell/compare/v5.6.0-March2018...v5.7.0-April2018

## 5.6.0 - March 2018

#### General
* Fix issue with Default Resource Group in CloudShell
* Fix issue where incorrect startup scripts were being executed during module import

#### AzureRM.Profile
* Enable MSI authentication in unsupported scenarios
* Add support for user-defined Managed Service Identity

#### AzureRM.AnalysisServices
* Fixed issue with cleaning up scripts in build

#### AzureRM.Cdn
* Fixed issue with cleaning up scripts in build

#### AzureRM.Compute
* 'New-AzureRmVM' and 'New-AzureRmVMSS' support data disks.
* 'New-AzureRmVM' and 'New-AzureRmVMSS' support custom image by name or by id.
* Log analytic feature
    - Added 'Export-AzureRmLogAnalyticRequestRateByInterval' cmdlet
    - Added 'Export-AzureRmLogAnalyticThrottledRequests' cmdlet

#### AzureRM.ContainerInstance
* Fix parameter sets issue for container registry and azure file volume mount

#### AzureRM.DataFactoryV2
* Updated the ADF .Net SDK to version 0.6.0-preview containing the following changes:
    - Added new AzureDatabricks LinkedService and DatabricksNotebook Activity
    - Added headNodeSize and dataNodeSize properties in HDInsightOnDemand LinkedService
    - Added LinkedService, Dataset, CopySource for SalesforceMarketingCloud
    - Added support for SecureOutput on all activities
    - Added new BatchCount property on ForEach activity which control how many concurrent activities to run
    - Added new Filter Activity
    - Added Linked Service Parameters support

#### AzureRM.Dns
* Support for Private DNS Zones (Public Preview)
    - Adds ability to create DNS zones that are visible only to the associated virtual networks

#### AzureRM.Network
* Updating model types for compatibility with DNS cmdlets.

#### AzureRM.RecoveryServices.SiteRecovery
* Changes for ASR Azure to Azure Site Recovery (cmdlets are currently supporting operations for Enterprise to Enterprise, Enterprise to Azure, HyperV to Azure,VMware to Azure)
    - New-AzureRmRecoveryServicesAsrProtectionContainer
    - New-AzureRmRecoveryServicesAsrAzureToAzureDiskReplicationConfig
    - Remove-AzureRmRecoveryServicesAsrProtectionContainer
    - Update-AzureRmRecoveryServicesAsrProtectionDirection

#### AzureRM.Storage
* Obsolete following parameters in new and set Storage Account cmdlets: EnableEncryptionService and DisableEncryptionService, since Encryption at Rest is enabled by default and can't be disabled.
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount

#### AzureRM.Websites
* Fixed the help for Remove-AzureRmWebAppSlot

## 5.5.0 - March 2018
#### AzureRM.Profile
* Fixed issue with importing aliases
* Load version 10.0.3 of Newtonsoft.Json side-by-side with version 6.0.8

#### Azure.Storage
* Support Soft-Delete feature
	- Enable-AzureStorageDeleteRetentionPolicy
	- Disable-AzureStorageDeleteRetentionPolicy
	- Get-AzureStorageBlob

#### AzureRM.AnalysisServices
* Fixed issue with importing aliases
* Add support of firewall and query scaleout feature, as well as support of 2017-08-01 api version.

#### AzureRM.Automation
* Fixed issue with importing aliases

#### AzureRM.Cdn
* Fixed issue with importing aliases

#### AzureRM.CognitiveServices
* Update notice.txt and notice message.

#### AzureRM.Compute
* 'New-AzureRmVMSS' prints connection strings in verbose mode.
* 'New-AzureRmVmss' supports public IP address, load balancing rules, inbound NAT rules.
* WriteAccelerator feature
    - Added WriteAccelerator switch parameter to the following cmdlets:
	  Set-AzureRmVMOSDisk
	  Set-AzureRmVMDataDisk
	  Add-AzureRmVMDataDisk
	  Add-AzureRmVmssDataDisk
    - Added OsDiskWriteAccelerator switch parameter to the following cmdlet:
          Set-AzureRmVmssStorageProfile.
    - Added OsDiskWriteAccelerator Boolean parameter to the following cmdlets:
          Update-AzureRmVM
          Update-AzureRmVmss

#### AzureRM.DataFactories
* Fix credential encryption issue that caused no meaningful error for some encryption operations
* Enable integration runtime to be shared across data factory

#### AzureRM.DataFactoryV2
* Add parameter "SetupScriptContainerSasUri" and "Edition" for "Set-AzureRmDataFactoryV2IntegrationRuntime" cmd to enable custom setup and edition selection functionality
* Fix credential encryption issue that caused no meaningful error for some encryption operations.
* Enable integration runtime to be shared across data factory

#### AzureRM.HDInsight
* Fixed issue with importing aliases

#### AzureRM.KeyVault
* Fixed example for Set-AzureRmKeyVaultAccessPolicy

#### AzureRM.Network
* Fixed issue with importing aliases

#### AzureRM.OperationalInsights
* Fixed issue with importing aliases

#### AzureRM.RecoveryServices
* Fixed issue with importing aliases

#### AzureRM.RecoveryServices.SiteRecovery
* Fixed issue with importing aliases

#### AzureRM.Resources
* Fixed issue with importing aliases

#### AzureRM.ServiceBus
* Added EnableBatchedOperations property to Queue
* Added DeadLetteringOnFilterEvaluationExceptions property to Subscriptions

#### AzureRM.ServiceFabric
* Service Fabric cmdlet refresh
  - Updated ARM templates
  - Failed operations no longer rollback
  - Add-AzureRmServiceFabricNodeType
    - VMs default to managed disks
    - Existing VMSS subnet used
    - All operations are idempotent
  - Remove-AzureRmServiceFabricNodeType cleans up partially created VMSS and/or cluster node types
  - Fixed output of PSCluster object for complex property types

#### AzureRM.Sql
* Fixed issue with importing aliases
* Get-AzureRmSqlServer, New-AzureRmSqlServer, and Remove-AzureRmSqlServer response now includes FullyQualifiedDomainName property.

#### AzureRM.Websites
* Fixed issue with importing aliases
* New-AzureRMWebApp - added parameter set for simplified WebApp creation, with local git repository support.

## 5.4.0 - February 2018
#### AzureRM.Automation
* Added alias from New-AzureRmAutomationModule to Import-AzureRmAutomationModule

#### AzureRM.Compute
* Fix ErrorAction issue for some of Get cmdlets.

#### AzureRM.ContainerInstance
* Apply Azure Container Instance SDK 2018-02-01
    - Support DNS name label

#### AzureRM.DevTestLabs
* Fixed all of the GET cmdlets which previously weren't working.

#### AzureRM.EventHub
* Fix bug in Get-AzureRmEventHubGeoDRConfiguration help

#### AzureRM.Network
* Added cmdlet to create a new connection monitor
    - New-AzureRmNetworkWatcherConnectionMonitor
* Added cmdlet to update a connection monitor
    - Set-AzureRmNetworkWatcherConnectionMonitor
* Added cmdlet to get connection monitor or connection monitor list
    - Get-AzureRmNetworkWatcherConnectionMonitor
* Added cmdlet to query connection monitor
    - Get-AzureRmNetworkWatcherConnectionMonitorReport
* Added cmdlet to start connection monitor
    - Start-AzureRmNetworkWatcherConnectionMonitor
* Added cmdlet to stop connection monitor
    - Stop-AzureRmNetworkWatcherConnectionMonitor
* Added cmdlet to remove connection monitor
    - Remove-AzureRmNetworkWatcherConnectionMonitor
* Updated Set-AzureRmApplicationGatewayBackendAddressPool documentation to remove deprecated example
* Added EnableHttp2 flag to Application Gateway
    - Updated New-AzureRmApplicationGateway: Added optional parameter -EnableHttp2
* Add IpTags to PublicIpAddress
    - Updated New-AzureRmPublicIpAddress: Added IpTags
    - New-AzureRmPublicIpTag to add Iptag
* Add DisableBgpRoutePropagation property in RouteTable and effectiveRoute.

#### AzureRM.Resources
* Register-AzureRmProviderFeature: Added missing example in the docs
* Register-AzureRmResourceProvider: Added missing example in the docs

#### AzureRM.Storage
* Obsolete following parameters in new and set Storage Account cmdlets: EnableEncryptionService and DisableEncryptionService, since Encryption at Rest is enabled by default and can't be disabled.
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount


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
  - Creating a new Alias (Disaster Recovery configuration):
    - `New-AzureRmEventHubGeoDRConfiguration`
  - Retrieve Alias (Disaster Recovery configuration) :
    - `Get-AzureRmEventHubGeoDRConfiguration`
  - Disabling the Disaster Recovery and stops replicating changes from primary to secondary namespaces
    - `Set-AzureRmEventHubGeoDRConfigurationBreakPair`
  - Invoking Disaster Recovery failover and reconfigure the alias to point to the secondary namespace
    - `Set-AzureRmEventHubGeoDRConfigurationFailOver`
  - Deleting an Alias(Disaster Recovery configuration)
    - `Remove-AzureRmEventHubGeoDRConfiguration`
* Added below new commands for checking the Namespace Name and GeoDr Configuration Name - Alias availability.
  - Check the Availability of Namespace name or Alias(Disaster Recovery configuration) name:
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
  - Creating a new Alias (Disaster Recovery configuration):
    - `New-AzureRmServiceBusDRConfigurations`
  - Retrieve Alias (Disaster Recovery configuration) :
    - `Get-AzureRmServiceBusDRConfigurations`
  - Disabling the Disaster Recovery and stops replicating changes from primary to secondary namespaces
    - `Set-AzureRmServiceBusDRConfigurationsBreakPairing`
  - Invoking Disaster Recovery failover and reconfigure the alias to point to the secondary namespace
    - `Set-AzureRmServiceBusDRConfigurationsFailOver`
  - Deleting an Alias(Disaster Recovery configuration)
    - `Remove-AzureRmServiceBusDRConfigurations`
* Updated `Test-AzureRmServiceBusName` commandlets to support Geo Disaster Recovery - Alias name check availability operations.
  - Check the Availability of Namespace name or Alias(Disaster Recovery configuration) name:
    - `Test-AzureRmServiceBusName`

### AzureRM.UsageAggregates
* Corrected usage of `Login-AzureRmAccount` to use `Connect-AzureRmAccount`

## 5.2.0 - January 2018
#### AzureRM.Profile
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Add-AzureRmAccount
  * Added -MSI login for authenticationg using the credentials of the Managed Service Identity of the current VM / Service
  * Fixed KeyVault Authentication when logging in with user-provided access tokens

#### Azure.Storage
* Add cmdlets to get and set Storage service properties
	- Get-AzureStorageServiceProperty
	- Update-AzureStorageServiceProperty

#### AzureRM.AnalysisServices
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.ApiManagement
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmApiManagementProperty, Set-AzureRmApiManagementProperty, and New-AzureRmApiManagement

#### AzureRM.ApplicationInsights
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Automation
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for Set-AzureRmAutomationRunbook

#### AzureRM.Backup
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Batch
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Cdn
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmCdnEndpoint and New-AzureRmCdnProfile

#### AzureRM.CognitiveServices
* Integrate with Cognitive Services Management SDK version 3.0.0.

#### AzureRM.Compute
* Added simplified parameter set to New-AzureRmVmss, which creates a Virtual Machine Scale Set and all required resources using smart defaults
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmVm and Update-AzureRmVm
* Fixed Get-AzureRmComputeResourceSku cmdlet when Zone is included in restriction.
* Updated Diagnostics Agent configuration schema for Azure Monitor sink support.

#### AzureRM.ContainerInstance
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.ContainerRegistry
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.DataFactories
* Enabled Azure Key Vault support for all data store linked services
* Added license type property for Azure SSIS integration runtime
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmDataFactory

#### AzureRM.DataFactoryV2
* Enabled Azure Key Vault support for all data store linked services
* Added license type property for Azure SSIS integration runtime
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Add parameter "LicenseType" for "Set-AzureRmDataFactoryV2IntegrationRuntime" cmd to enable AHUB functionality

#### AzureRM.DataLakeAnalytics
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmDataLakeAnalyticsAccount and Set-AzureRmDataLakeAnalyticsAccount

#### AzureRM.DataLakeStore
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmDataLakeStoreAccount and Set-AzureRmDataLakeStoreAccount

#### AzureRM.DevTestLabs
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Dns
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.EventGrid
* Added the following new cmdlet:
  - Update-AzureRmEventGridSubscription
    - Update the properties of an Event Grid event subscription.
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.EventHub
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.HDInsight
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Insights
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.IotHub
* Add Certificate support for IoTHub cmdlets
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.KeyVault
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Added -AsJob support for long-running KeyVault cmdlets. Allows selected cmdlets to run in the background and return a job to track and control progress.
  * Affected cmdlet is: Remove-AzureRmKeyVault
* Fixed bug in Set-AzureRmKeyVaultAccessPolicy where the AAD filter was setting SPN to the provided UPN, rather than setting the UPN
  - See the following issue for more information: https://github.com/Azure/azure-powershell/issues/5201

#### AzureRM.LogicApp
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.MachineLearning
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for Update-AzureRmMlCommitmentPlan

#### AzureRM.MachineLearningCompute
* Add IncludeAllResources parameter to Remove-AzureRmMlOpCluster cmdlet
  - Using this switch parameter will remove all resources that were created with the cluster originally
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Media
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for Set-AzureRmMediaService and New-AzureRmMediaService

#### AzureRM.Network
* Added -AsJob support for long-running Network cmdlets. Allows selected cmdlets to run in the background and return a job to track and control progress.
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.NotificationHubs
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmNotificationHubsNamespace and Set-AzureRmNotificationHubsNamespace

#### AzureRM.OperationalInsights
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmOperationalInsightsSavedSearch, Set-AzureRmOperationalInsightsSavedSearch, New-AzureRmOperationalInsightsWorkspace, and Set-AzureRmOperationalInsightsWorkspace

#### AzureRM.PowerBIEmbedded
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.RecoveryServices
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.RecoveryServices.Backup
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Added -UseOriginalStorageAccount option to the Restore-AzureRmRecoveryServicesBackupItem cmdlet.
  - Enabling this flag results in restoring disks to their original storage accounts which allows users to maintain the configuration of restored VM as close to the original VMs as possible.
  - It also helps in improving the performance of the restore operation.

#### AzureRM.RedisCache
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Added  3 new cmdlets for firewall rules
* Added  3 new cmdlets for geo replication
* Added support for zones and tags
* Make ResourceGroup as optional whenever possible.

#### AzureRM.Relay
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Resources
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Added -AsJob support for long-running Resources cmdlets. Allows selected cmdlets to run in the background and return a job to track and control progress.
* Added alias from Get-AzureRmProviderOperation to Get-AzureRmResourceProviderAction to conform with naming conventions

#### AzureRM.Scheduler
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.ServerManagement
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Obsoleted -Tags in favor of -Tag for New-AzureRmServerManagementNode and New-AzureRmServerManagementGateway

#### AzureRM.ServiceBus
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.ServiceFabric
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.SiteRecovery
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Sql
* Update the Auditing commands parameters description
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Added -AsJob parameter to long running cmdlets
* Obsoleted -DatabaseName parameter from Get-AzureRmSqlServiceObjective

#### AzureRM.Storage
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Fix a null reference issue of run cmdlet New-AzureRMStorageAccount with parameter -EnableEncryptionService None
* Added -AsJob support for long-running Storage cmdlets. Allows selected cmdlets to run in the background and return a job to track and control progress.
    - Affected cmdlets are New-, Remove-, Add-, and Update- for Storage Account and Storage Account Network Rule.

#### AzureRM.StreamAnalytics
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.TrafficManager
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription

#### AzureRM.Websites
* Added Location Completer to -Location parameters allowing tab completion through valid Locations
* Added ResourceGroup Completer to -ResourceGroup parameters allowing tab completion through resource groups in current subscription
* Added -AsJob support for long-running Websites cmdlets. Allows selected cmdlets to run in the background and return a job to track and control progress.
     - Affected cmdlets are New-, Remove-, Add-, and Set- for WebApps, AppServicePlan and Slots

## 2017.12.8 Version 5.1.1
* AnalysisServices
  - Change validate set of location to dynamic lookup so that all clouds are supported.
* Automation
  - Update to Import-AzureRMAutomationRunbook
    - Support is now being provided for Python2 runbooks
* Batch
  - Fixed a bug where account operations without a resource group failed to auto-detect the resource group
* Compute
  - Get-AzureRmComputeResourceSku shows zone information.
  - Update Disable-AzureRmVmssDiskEncryption to fix issue https://github.com/Azure/azure-powershell/issues/5038
  - Added -AsJob support for long-running Compute cmdlets. Allows selected cmdlets to run in the background and return a job to track and control progress.
    - Affected cmdlets include: New-, Update-, Set-, Remove-, Start-, Restart-, Stop- cmdlets for Virtual Machines and Virtual Machine Scale Sets
    - Added simplified parameter set to New-AzureRmVM, which creates a Virtual Machine and all required resources using smart defaults
* ContainerInstance
  - Apply Azure Container Instance SDK 2017-10-01
    - Support container run-to-completion
    - Support Azure File volume mount
    - Support opening multiple ports for public IP
* ContainerRegistry
  - New cmdlets for geo-replication and webhooks
    - Get/New/Remove-AzureRmContainerRegistryReplication
    - Get/New/Remove/Test/Update-AzureRmContainerRegistryWebhook
* DataFactories
    - Credential encryption functionality now works with both "Remote Access" enabled (Over Network) and "Remote Access" disabled (Local Machine).
* DataFactoryV2
  - Added two new cmdlets: Update-AzureRmDataFactoryV2 and Stop-AzureRmDataFactoryV2PipelineRun
* DataLakeAnalytics
  - Added a parameter called ScriptParameter to Submit-AzureRmDataLakeAnalyticsJob
    - Detailed information about ScriptParameter can be found using Get-Help on Submit-AzureRmDataLakeAnalyticsJob
  - For New-AzureRmDataLakeAnalyticsAccount, changed the parameter MaxDegreeOfParallelism to MaxAnalyticsUnits
    - Added an alias for the parameter MaxAnalyticsUnits: MaxDegreeOfParallelism
  - For New-AzureRmDataLakeAnalyticsComputePolicy, changed the parameter MaxDegreeOfParallelismPerJob to MaxAnalyticsUnitsPerJob
    - Added an alias for the parameter MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
  - For Set-AzureRmDataLakeAnalyticsAccount, changed the parameter MaxDegreeOfParallelism to MaxAnalyticsUnits
    - Added an alias for the parameter MaxAnalyticsUnits: MaxDegreeOfParallelism
  - For Submit-AzureRmDataLakeAnalyticsJob, changed the parameter DegreeOfParallelism to AnalyticsUnits
    - Added an alias for the parameter AnalyticsUnits: DegreeOfParallelism
  - For Update-AzureRmDataLakeAnalyticsComputePolicy, changed the parameter MaxDegreeOfParallelismPerJob to MaxAnalyticsUnitsPerJob
    - Added an alias for the parameter MaxAnalyticsUnitsPerJob: MaxDegreeOfParallelismPerJob
* MachineLearningCompute
  - Add Set-AzureRmMlOpCluster
    - Update a cluster's agent count or SSL configuration
  - Orchestrator properties are optional
    - The service will create a service principal if not provided, so the orchestrator properties are now optional
* PowerBIEmbedded
  - Add support for Power BI Embedded Capacity cmdlets
  - New Cmdlet Get-AzureRmPowerBIEmbeddedCapacity - Gets the details of a PowerBI Embedded Capacity.
  - New Cmdlet New-AzureRmPowerBIEmbeddedCapacity - Creates a new PowerBI Embedded Capacity
  - New Cmdlet Remove-AzureRmPowerBIEmbeddedCapacity - Deletes an instance of PowerBI Embedded Capacity
  - New Cmdlet Resume-AzureRmPowerBIEmbeddedCapacity - Resumes an instance of PowerBI Embedded Capacity
  - New Cmdlet Suspend-AzureRmPowerBIEmbeddedCapacity - Suspends an instance of PowerBI Embedded Capacity
  - New Cmdlet Test-AzureRmPowerBIEmbeddedCapacity - Tests the existence of an instance of PowerBI Embedded Capacity
  - New Cmdlet Update-AzureRmPowerBIEmbeddedCapacity - Modifies an instance of PowerBI Embedded Capacity
* Profile
  - Updated USGovernmentActiveDirectoryEndpoint to https://login.microsoftonline.us/
    - For more information about the Azure Government endpoint mappings, please see the following: https://docs.microsoft.com/azure/azure-government/documentation-government-developer-guide#endpoint-mapping
    - Added -AsJob support for cmdlets, enabling selected cmdlets to execute in the background and return a job to track and control progress
    - Added -AsJob parameter to Get-AzureRmSubscription cmdlet
* RecoveryServices.Backup
  - Fixed bug - Get-AzureRmRecoveryServicesBackupItem should do case insensitive comparison for container name filter.
  - Fixed bug - AzureVmItem now has a property that shows the last time a backup operation has happened - LastBackupTime.
* Resources
  - Fixed issue where Get-AzureRMRoleAssignment would result in a assignments without roledefiniton name for custom roles
    - Users can now use Get-AzureRMRoleAssignment with assignments having roledefinition names irrespective of the type of role
  - Fixed issue where Set-AzureRMRoleRoleDefinition used to throw RD not found error when there was a new scope in assignablescopes
    - Users can now use Set-AzureRMRoleRoleDefinition with assignable scopes including new scopes irrespective of the position of the scope
  - Allow scopes to end with "/"
    - Users can now use RoleDefinition and RoleAssignment commandlets with scopes ending with "/" ,consistent with API and CLI
  - Allow users to create RoleAssignment using delegation flag
    - Users can now use New-AzureRMRoleAssignment with an option of adding the delegation flag
  - Fix RoleAssignment get to respect the scope parameter
  - Add an alias for ServicePrincipalName in the New-AzureRmRoleAssignment Commandlet
    - Users can now use the ApplicationId instead of the ServicePrincipalName when using the New-AzureRmRoleAssignment commandlet
* SiteRecovery
  - Add deprecation warnings for all cmdlets in this module in preparation for the next breaking change release.
    - Please see the upcoming breaking changes guide for more information on how to migrate your cmdlets from AzureRM.
* Sql
  - Added ability to rename database using Set-AzureRmSqlDatabase
  - Fixed issue https://github.com/Azure/azure-powershell/issues/4974
    - Providing invalid AUDIT_CHANGED_GROUP value for auditing cmdlets no longer throws an error and will be removed in an upcoming release.
  - Fixed issue https://github.com/Azure/azure-powershell/issues/5046
    - AuditAction parameter in auditing cmdlets is no longer being ignored
  - Fixed an issue in Auditing cmdlets when 'Secondary' StorageKeyType is provided
    - When setting blob auditing, the primary storage account key was used instead of the secondary key when providing 'Secondary' value for StorageKeyType parameter.
  - Changing the wording for confirmation message from Set-AzureRmSqlServerTransparentDataEncryptionProtector
* Azure (RDFE)
    - Removed all RemoteApp Cmdles
* Azure.Storage
    - Upgrade to Azure Storage Client Library 8.6.0 and Azure Storage DataMovement Library 0.6.5

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
