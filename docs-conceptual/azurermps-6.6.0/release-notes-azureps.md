---
title: Azure PowerShell Change Log | Microsoft Docs
description: This is a history of changes made to Azure PowerShell in the latest release.
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
## 6.6.0 - July 2018
#### General
* Updated all help files to include full parameter types and correct input/output types.

#### AzureRM.Profile
* Updated Common.Strategy library to be able to validate that the current config for a resource is compatible with the target resource. Default is always true, individual resources and overridet the default.
* Added ps1xml types to Common.Storage

#### Azure.Storage
* Support get Storage Context from DefaulfProfile
* Add Ps1XmlAttribute to cmdlets output types properties.

#### AzureRM.ApiManagement
* Fixed issue https://github.com/Azure/azure-powershell/issues/6370
    - Fixed bug in Automapper to translate PsApiManagementApi to ApiContract
* Fixed issue https://github.com/Azure/azure-powershell/issues/6515
    - Fixed bug in File.Save to not overload with Encoding Type
* Fixed issue https://github.com/Azure/azure-powershell/issues/6560
    - Upgraded to 4.0.3 Nuget version which fixes the pattern exception on apiId

#### AzureRM.Compute
* Fix issue with creating a vm using DiskFileParameterSet in New-AzureRmVm failing because of PremiumLRS storage account type renaming.
* Fix Invoke-AzureRmVMRunCommand cmdlet
* Update Get-AzureRmAvailabilitySet to enable list all availability sets in a subscription.  (ResouceGroupName parameter is now optional.)
* Update SimpleParameterSet of 'New-AzureRmVm' to enable Accelerated Network on qualifying vms.
* Update New-AzureRmVmss simple parameter set to fail creating the vmss when a user specified LB already exists.
* Update example for New-AzureRmDisk
* Add example for 'New-AzureRmVM'
* Update description for Set-AzureRmVMOSDisk
* Update Example 1 for Set-AzureRmVMBginfoExtension to correct spelling and prefix. 

#### AzureRM.DataFactoryV2
* Updated the ADF .Net SDK version to 1.1.0.
* Support self-hosted integration runtime sharing across data factories.
     - Add new parameter -SharedIntegrationRuntimeResourceId to Set-AzureRmDataFactoryV2IntegrationRuntime cmdlet.
     - Add new optional parameter -LinkedDataFactoryName to Remove-AzureRmDataFactoryV2IntegrationRuntime cmdlet.

#### AzureRM.DataLakeStore
* Updated the DataPlane SDK (Microsoft.Azure.DataLake.Store) version to 1.1.9

#### AzureRM.EventHub
* Updated piping for InputObject and ResourceId in remove cmdlets

#### AzureRM.Insights
* Fixed formatting of OutputType in help files
* Using Microsoft.Azure.Management.Monitor SDK 0.19.1-preview

#### AzureRM.KeyVault
* Fix piping issue in Set-AzureRmKeyVaultAccessPolicy

#### AzureRM.Network
* Added examples for LoadBalancerInboundNatPoolConfig cmdlets.

#### AzureRM.Resources
* Fix issue when providing both tag name and value for 'Get-AzureRmResource'
    - https://github.com/Azure/azure-powershell/issues/6765
* Fix piping scenario with 'Set-AzureRmResource'

#### AzureRM.ServiceBus
* Updated piping for InputObject and ResourceId in remove cmdlets
* fixed few issues
	- https://github.com/Azure/azure-powershell/issues/3780
	- https://github.com/Azure/azure-powershell/issues/4340

#### AzureRM.Sql
* Adding Server Advanced Threat Protection support with the following cmdlets:
	- Enable-AzureRmSqlServerAdvancedThreatProtection; Disable-AzureRmSqlServerAdvancedThreatProtection; Get-AzureRmSqlServerAdvancedThreatProtectionPolicy
* Adding Vulnerability Assessment support with the following cmdlets:
	- Update-AzureRmSqlDatabaseVulnerabilityAssessmentSettings; Get-AzureRmSqlDatabaseVulnerabilityAssessmentSettings; Clear-AzureRmSqlDatabaseVulnerabilityAssessmentSettings
	- Set-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline; Get-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline; Clear-AzureRmSqlDatabaseVulnerabilityAssessmentRuleBaseline
	- Convert-AzureRmSqlDatabaseVulnerabilityAssessmentScan; Get-AzureRmSqlDatabaseVulnerabilityAssessmentScanRecord; Start-AzureRmSqlDatabaseVulnerabilityAssessmentScan
* Fixed example in Remove-AzureRmSqlServerFirewallRule
* Fix datetime handling incorrectly for non-us base culture in Get-AzureSqlSyncGroupLog

#### AzureRM.Storage
* Add Ps1XmlAttribute to cmdlets output types properties
* Show StorageAccount cmdlet output in table view
    - Get-AzureRmStorageAccount
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount

#### AzureRM.Tags
* Remove incorrect statement from Tag cmdlet help
    - https://github.com/Azure/azure-powershell/issues/3878

## 6.5.0 - July 2018
#### AzureRM.Profile
* Updated help for 'Get-AzureRmContextAutosaveSetting'

#### Azure.Storage
* Support Upload Blob or File with write only Sas token
- Set-AzureStorageBlobContent
- Set-AzureStorageFileContent

#### AzureRM.AnalysisServices
* Add required property ResourceGroupName to AS.

#### AzureRM.Automation
* Update help and add example for 'New-AzureRMAutomationSchedule'

#### AzureRM.Compute
* Add -Tag parameter to Update/New-AzureRmAvailabilitySet
* Add example for 'Add-AzureRmVmssExtension'
* Add examples for 'Remove-AzureRmVmssExtension'
* Update help for 'Set-AzureRmVMAccessExtension'
* Update SimpleParameterSet for New-AzureRmVmss to set SinglePlacementGroup to false by default and add switch parameter 'SinglePlacementGroup' that enables the user to create the VMSS in a single placement group.

#### AzureRM.EventHub
* Added a readonly property 'PendingReplicationOperationsCount' to PSEventHubDRConfigurationAttributes class, which gives the pending replication operations count while replication is in progress

#### AzureRM.KeyVault
* Update error message for Set-AzureRmKeyVaultAccessPolicy

#### AzureRM.LogicApp
* Fixed "parameter set could not be resolved" error in New-AzureRmLogicApp

#### AzureRM.Network
* Enable peering across Virtual Networks in multiple Tenants for Set/Add-AzureRmVirtualNetworkPeering
* Updated below cmdlets for Application Gateway
    - New-AzureRmApplicationGateway : Added EnableFIPS flag and Zones support
    - New-AzureRmApplicationGatewaySku : Added new skus Standard_v2 and WAF_v2
    - Set-AzureRmApplicationGatewaySku : Added new skus Standard_v2 and WAF_v2
* Regenerated RouteTable cmdlets with the latest generator version

#### AzureRM.Relay
* Updated markdown files, fix for the parameter name issue in example

#### AzureRM.Resources
* Update Roleassignment and roledefinition cmdlets:
    - Remove extra roledefinition calls done as part of paging.
* Fix Get-AzureRmRoleAssignment cmdlet
    - Fix -ExpandPrincipalGroups command parameter functionality
* Fix issue with 'Get-AzureRmResource' where '-ResourceType' parameter was case sensitive

#### AzureRM.ServiceBus
* Added top and skip parameter to list cmdlets
* Added Standard to Premium NameSpace migration cmdlets :
	- Start-AzureRmServiceBusMigration
	- Get-AzureRmServiceBusMigration
	- Complete-AzureRmServiceBusMigration
	- Stop-AzureRmServiceBusMigration
	- Remove-AzureRmServiceBusMigration
* Added a readonly property 'PendingReplicationOperationsCount' to PSServiceBusDRConfigurationAttributes class, which gives the pending replication operations count while replication is in progress

#### AzureRM.ServiceFabric
* Update example for 'New-AzureRmServiceFabricCluster'

#### AzureRM.Sql
* Adding new Cmdlets for Management.Sql to allow customers to add TDE Certificate to Sql Server instance or a Managed Instance
	- Add-AzureRmSqlServerTransparentDataEncryptionCertificate
	- Add-AzureRmSqlManagedInstanceTransparentDataEncryptionCertificate

#### AzureRM.Websites
* `Set-AzureRmWebApp -AssignIdentity` and  `Set-AzureRmWebAppSlot -AssignIdentity` when set to false will now remove the Identity property from the site object.Removing preview tag as well.
* `Get-AzureRmWebAppMetrics`,`Get-AzureRmAppServicePlanMetrics` example updated
* `Set-AzureRmWebApp -PhpVersion` supports off as a valid php version

## 6.4.0 - July 2018
#### General
* Fixed formatting of OutputType in help files for most modules

#### AzureRM.Profile
* Ps1Xml attribute added to the basic output types

#### AzureRM.Compute
* IP Tag feature for VMSS
    - 'New-AzureRmVmssIpTagConfig' cmdlet is added
    - IpTag parameter is added to New-AzureRmVmssIpConfig
* Auto OS Rollback feature for VMSS
    - DisableAutoRollback parameters are added to New-AzureRmVmssConfig and Update-AzureRmVmss
* OS Upgrade History feature for Vmss
    - OSUpgradeHistory switch parameter is added to Get-AzureRmVmss

#### AzureRM.DataLakeAnalytics
* Add support for Catalog ACLs through the following commands:
    - Get-AzureRmDataLakeAnalyticsCatalogItemAclEntry
    - Set-AzureRmDataLakeAnalyticsCatalogItemAclEntry
    - Remove-AzureRmDataLakeAnalyticsCatalogItemAclEntry

#### AzureRM.DataLakeStore
* Add cancellation support and progress tracking for Set-AzureRmDataLakeStoreItemAclEntry, Remove-AzureRmDataLakeStoreItemAclEntry, Set-AzureRmDataLakeStoreItemAcl
* Add cancellation support for Export-AzureRmDataLakeStoreChildItemProperties
* Fix flushing of debug messages for cmdlets that does recursive operations
* Fix location of test of DataLake cmdlets

#### AzureRM.EventHub
* Added Optional MaxCount parameter to List Operations cmdlet Get-AzureRmEventHub and Get-AzureRmEventHubConsumerGroup
* Fixed issue in New-AzureRmEventHub cmdlet where at least one parameter needed while creating New EventHub. Provided Default Parameter set.
* Added optional Parameter -KeyValue to New-AzureRmEventHubKey cmdlet, which enables user to provide KeyValue.

#### AzureRM.KeyVault
* Fix issue where all resources were being returned by Get-AzureRmKeyVault -Tag

#### AzureRM.Network
* Expose new Skus for Zone-Redundant VirtualNetworkGateways
* Added new commands for feature: ExpressRoute Partner APIs via ARM
    - Added Get-AzureRmExpressRouteCrossConnection
    - Added Set-AzureRmExpressRouteCrossConnection
    - Added Add-AzureRmExpressRouteCrossConnectionPeering
    - Added Get-AzureRmExpressRouteCrossConnectionPeering
    - Added Remove-AzureRmExpressRouteCrossConnectionPeering
    - Added Get-AzureRMExpressRouteCrossConnectionArpTable
    - Added Get-AzureRMExpressRouteCrossConnectionRouteTable
    - Added Get-AzureRMExpressRouteCrossConnectionRouteTableSummary

#### AzureRM.RecoveryServices.Backup
* Added Get-AzureRmRecoveryServicesBackupStatus cmdlet. This cmdlet takes a VM ID and checks if the VM is protected by some vault in the subscription. If there exists such a vault, the cmdlet outputs the vault details.

#### AzureRM.Resources
* Update Get-AzureRmPolicyAssignment cmdlets:
    - Add support for listing -Scope values at management group level
    - Add support for retrieving individual assignments with -Scope values at management group level
    - Add -Effective and -All switches to control  parameter
* Update Get/New/Remove/Set-AzureRmPolicyDefinition cmdlets
    - Add -ManagementGroupName parameter to apply operations to a given management group
    - Add -SubscriptionId parameter to apply operations to a given subscription
* Update Get/New/Remove/Set-AzureRmPolicySetDefinition cmdlets
    - Add -ManagementGroupName parameter to apply operations to a given management group
    - Add -SubscriptionId parameter to apply operations to a given subscription
* Add KeyVault secret reference support in parameters when using 'TemplateParameterObject' in 'New-AzureRmResourceGroupDeployment'
* Fix issue where '-EndDate' parameter was ignored for 'New-AzureRmADAppCredential'
    - https://github.com/Azure/azure-powershell/issues/6505
* Fix issue where 'Add-AzureRmADGroupMember' used incorrect URL to make request
    - https://github.com/Azure/azure-powershell/issues/6485

#### AzureRM.ServiceBus
* Added optional Parameter -KeyValue to New-AzureRmServiceBusKey cmdlet, which enables user to provide KeyValue.

#### AzureRM.Sql
* Clarified User-Defined Restore Points for SQLDW in New-AzureRmSqlDatabaseRestorePoint help
* Updated documentation of -ComputeGeneration parameter in several cmdlets

## 6.3.0 - June 2018
#### AzureRM.Profile
* Updated error messages for Enable-AzureRmContextAutoSave
* Create a context for each subscription when running 'Connect-AzureRmAccount' with no previous context

#### Azure.Storage
* Added additional information about -Permissions parameter in help files.

#### AzureRM.Compute
* 'Get-AzureRmVmDiskEncryptionStatus' fixes an issue observed for VMs with no data disks 
* Update Compute client library version to fix following cmdlets
    - Grant-AzureRmDiskAccess
    - Grant-AzureRmSnapshotAccess
    - Save-AzureRmVMImage
* Fixed following cmdlets to show 'operation ID' and 'operation status' correctly:
    - Start-AzureRmVM
    - Stop-AzureRmVM
    - Restart-AzureRmVM
    - Set-AzureRmVM
    - Remove-AzuerRmVM
    - Set-AzureRmVmss
    - Start-AzureRmVmssRollingOSUpgrade
    - Stop-AzureRmVmssRollingUpgrade
    - Start-AzureRmVmss
    - Restart-AzureRmVmss
    - Stop-AzureRmVmss
    - Remove-AzureRmVmss
    - ConvertTo-AzureRmVMManagedDisk
    - Revoke-AzureRmSnapshotAccess
    - Remove-AzureRmSnapshot
    - Revoke-AzureRmDiskAccess
    - Remove-AzureRmDisk
    - Remove-AzureRmContainerService
    - Remove-AzureRmAvailabilitySet

#### AzureRM.EventGrid
* Remove ValidateNotNullOrEmpty validation conditions for SubjectBeginsWith/SubjectEndsWith in Update-AzureRmEventGridSubscription cmdlet to allow changing these parameters to empty string if needed.

#### AzureRM.KeyVault
* Fix issue where no Tags are being returned when Get-AzureRmKeyVault -Tag is run

#### AzureRM.PolicyInsights
* Public release of Policy Insights cmdlets
    - Use API version 2018-04-04
    - Add PolicyDefinitionReferenceId to the results of Get-AzureRmPolicyStateSummary

#### AzureRM.RecoveryServices.Backup
* Added -Vault parameter to RecoveryServices.Backup cmdlets. When passed, this will override the Set-AzureRmRecoveryServicesContext cmdlet.

#### AzureRM.Sql
* Updated example in the help file for Get-AzureRmSqlDatabaseExpanded

#### AzureRM.TrafficManager
* Updated the help file for Add-AzureRmTrafficManagerEndpointConfig

#### AzureRM.Websites
* 'Set-AzureRmWebApp' is updated to not overwrite the AppSettings when using -AssignIdentity
* 'New-AzureRmWebAppSlot' is updated to honor AppServicePlan as an optional parameter

## 6.2.1 - June 2018
### AzureRM.OperationalInsights
* Updated PSWorkspace model to allow Network to use type as a parameter

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