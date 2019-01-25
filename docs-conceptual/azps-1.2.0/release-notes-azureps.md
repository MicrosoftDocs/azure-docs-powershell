## 1.2.0 - January 2019
#### Az.Accounts
* Add interactive and username/password authentication for Windows PowerShell 5.1 only
* Update incorrect online help URLs
* Add warning message in PS Core for Uninstall-AzureRm

#### Az.Aks
* Update incorrect online help URLs

#### Az.Automation
* Added support for Python 2 runbooks
* Update incorrect online help URLs

#### Az.Cdn
* Update incorrect online help URLs

#### Az.Compute
* Add Invoke-AzVMReimage cmdlet
* Add TempDisk parameter to Set-AzVmss
* Fix the warning message of New-AzVM

#### Az.ContainerRegistry
* Update incorrect online help URLs

#### Az.DataFactory
* Updated ADF .Net SDK version to 3.0.0

#### Az.DataLakeStore
* Fix issue with ADLS endpoint when using MSI
    - More information here: https://github.com/Azure/azure-powershell/issues/7462
* Update incorrect online help URLs

#### Az.IotHub
* Add Encoding format to Add-IotHubRoutingEndpoint cmdlet.

#### Az.KeyVault
* Update incorrect online help URLs

#### Az.Network
* Update incorrect online help URLs

#### Az.Resources
* Fix incorrect examples in 'New-AzADAppCredential' and 'New-AzADSpCredential' reference documentation
* Fix issue where path for '-TemplateFile' parameter was not being resolved before executing resource group deployment cmdlets
* Az.Resources: Correct documentation for New-AzureRmPolicyDefinition -Mode default value
* Az.Resources: Fix for issue https://github.com/Azure/azure-powershell/issues/7522
* Az.Resources: Fix for issue https://github.com/Azure/azure-powershell/issues/5747
* Fix formatting issue with 'PSResourceGroupDeployment' object
    - More information here: https://github.com/Azure/azure-powershell/issues/2123

#### Az.ServiceFabric
* Rollback when a certificate is added to VMSS model but an exception is thrown this is to fix bug: https://github.com/Azure/service-fabric-issues/issues/932
* Fix some error messages.
* Fix create cluster with default ARM template for New-AzServiceFabriCluster which was not working with migration to Az.
* Fix add cluster/application certificate to only add to VM Scale Sets that correspond to the cluster by checking cluster id in the extension.

#### Az.SignalR
* Update incorrect online help URLs

#### Az.Sql
* Update incorrect online help URLs
* Updated parameter description for LicenseType parameter with possible values
* Fix for updating managed instance identity not working when it is the only updated property
* Support for custom collation on managed instance

#### Az.Storage
* Update incorrect online help URLs
* Give detail error message when get/set classic Logging/Metric on Premium Storage Account, since Premium Storage Account not supoort classic Logging/Metric.
    - Get/Set-AzStorageServiceLoggingProperty
    - Get/Set-AzStorageServiceMetricsProperty

#### Az.TrafficManager
* Update incorrect online help URLs

#### Az.Websites
* Update incorrect online help URLs
* Fixes 'New-AzWebAppSSLBinding' to upload the certificate to the correct resourcegroup+location if the app is hosted on an ASE.
* Fixes 'New-AzWebAppSSLBinding' to not overwrite the tags on binding an SSL certificate to an app

## 1.1.0 - January 2019
#### Az.Accounts
* Add 'Local' Scope to Enable-AzureRmAlias

#### Az.Compute
* Name is now optional in ID parameter set for Restart/Start/Stop/Remove/Set-AzVM and Save-AzVMImage
* Updated the description of ID in help files
* Fix backward compatibility issue with Az.Accounts module

#### Az.DataLakeStore
* Update the sdk version of dataplane to 1.1.14 for SDK fixes.
    - Fix handling of negative acesstime and modificationtime for getfilestatus and liststatus, Fix async cancellation token

#### Az.EventGrid
* Updated to use the 2019-01-01 API version.
* Update the following cmdlets to support new scenario in 2019-01-01 API version
    - New-AzureRmEventGridSubscription: Add new optional parameters for specifying:
        - Event Time-To-Live,
        - Maximum number of delivery attempts for the events,
        - Dead letter endpoint.
    - Update-AzureRmEventGridSubscription: Add new optional parameters for specifying:
        - Event Time-To-Live,
        - Maximum number of delivery attempts for the events,
        - Dead letter endpoint.
* Add new enum values (namely, storageQueue and hybridConnection) for EndpointType option in New-AzureRmEventGridSubscription and Update-AzureRmEventGridSubscription cmdlets.
* Show warning message if creating or updating the event subscription is expected to entail manual action from user.

#### Az.IotHub
* Updated to the latest version of the IotHub SDK

#### Az.LogicApp
* Get-AzLogicApp lists all without specified Name

#### Az.Resources
* Fix parameter set issue when providing '-ODataQuery' and '-ResourceId' parameters for 'Get-AzResource'
    - More information here: https://github.com/Azure/azure-powershell/issues/7875
* Fix handling of the -Custom parameter in New/Set-AzPolicyDefinition
* Fix typo in New-AzDeployment documentation
* Made '-MailNickname' parameter mandatory for 'New-AzADUser'
    - More information here: https://github.com/Azure/azure-powershell/issues/8220

#### Az.SignalR
* Fix backward compatibility issue with Az.Accounts module

#### Az.Sql
* Converted the Storage management client dependency to the common SDK implementation.

#### Az.Storage
* Set the StorageAccountName of Storage context as the real Storage Account Name, when it's created with Sas Token, OAuth or Anonymous
    - New-AzStorageContext
* Create Sas Token of Blob Snapshot Object with '-FullUri' parameter, fix the returned Uri to be the sanpshot Uri
    - New-AzStorageBlobSASToken

#### Az.Websites
* Fixed a date parsing bug in 'Get-AzDeletedWebApp'
* Fix backward compatibility issue with Az.Accounts module

## 1.0.0 - December 2018
### General

- General Availability of Az Module
- Online help for each module
- For more details and a roadmap, see the [Az Announcement page](https://aka.ms/azps-announce)
- See the [Migration Guide](https://aka.ms/azps-migration-guide) for information on migrating from AzureRM

### Az.Accounts
- Changed from Az.Profile
- Fixed table formats for profile and context types

### Az.ApiManagement
- Fixes for #7002
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.Batch
- Added the ability to see what version of the Azure Batch Node Agent is running on each of the VMs in a pool, via the new `NodeAgentInformation` property on `PSComputeNode`.
- The `Caching` default for `PSDataDisk` is now `ReadWrite` instead of `None`.
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.Billing
- Combines Billing, Consumption, and UsageAggregates cmdlets, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.CognitivServices
- Add completers for SkuName and Typem available on New-AzureRmCognitiveServicesAccount operation
- Removed GetSkusWithAccountParamSetName parameter set from Get-AzCognitiveServicesAccountSkus

### Az.ContainerInstance
- Added ManagedIdentity support

### Az.DataLakeAnalytics
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.DataLakeStore
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.Monitor
- Renamed Az.Insights to Az.Monitor and other minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.KeyVault
- Removed the deprecated 'PurgeDisabled' property from output types

### Az.MachineLearning
- Included cmdlets from Az.MachineLearningCompute module

### Az.Media
- Remove deprecated -Tags alias from New-AzMediaService

### Az.Network
Added support for the configuring RewriteRuleSets in the Application Gateway
    - New cmdlets added:
        - Add-AzureRmApplicationGatewayRewriteRuleSet
        - Get-AzureRmApplicationGatewayRewriteRuleSet
        - New-AzureRmApplicationGatewayRewriteRuleSet
        - Remove-AzureRmApplicationGatewayRewriteRuleSet
        - Set-AzureRmApplicationGatewayRewriteRuleSet
        - New-AzureRmApplicationGatewayRewriteRule
        - New-AzureRmApplicationGatewayRewriteRuleActionSet
        - New-AzureRmApplicationGatewayRewriteRuleHeaderConfiguration
    - Cmdlets updated with optional parameter -RewriteRuleSet
        - New-AzureRmApplicationGateway
        - New-AzureRmApplicationGatewayRequestRoutingRule
        - Add-AzureRmApplicationGatewayRequestRoutingRule
        - New-AzureRmApplicationGatewayPathRuleConfig
        - Add-AzureRmApplicationGatewayUrlPathMapConfig
        - New-AzureRmApplicationGatewayUrlPathMapConfig
Added KeyVault Support to Application Gateway using Identity.
    - Cmdlets updated with optonal parameter -KeyVaultSecretId, -KeyVaultSecret
        - Add-AzApplicationGatewaySslCertificate
        - New-AzApplicationGatewaySslCertificate
        - Set-AzApplicationGatewaySslCertificate
    - New-AzApplicationGateway cmdlet updated with optional parameter -UserAssignedIdentity
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.OperationalInsights
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.Profile
- Changed module name to Az.Accounts

### Az.RecoveryServices
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.Resources
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.ServiceFabric
- Support specfying certificate by common name and thumbprint
- Mnor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.SIgnalR
- General Availability for PowerShell cmdlets for SIgnalR

### Az.Sql
- Added new Data_Exfiltration and Unsafe_Action detection types to Threat Detection's cmdlets
- Updated documentation examples for Sql Auditing cmdlets
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.Storage
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

### Az.Websites
- Minor breaking changes, see the [Migration Guide](https://aka.ms/azps-migration-guide)  for details

## 0.7.0 - December 2018

### General

* Minor changes for upcoming AzureRM to Az transition

### Az.Compute

* Add support for UltraSSD and Gallery Images in the simple param sets for `New-AzVm(ss)` cmdlets.

### Az.DataLakeStore

* Fix the trailing slash of the domain of adls account

### Az.FrontDoor

* Fixed some broken links
    - In the New-AzureRmFrontDoor and Set-AzureRmFrontDoor articles, fixed the link to the New-AzureRmFrontDoorHealthProbeSettingObject cmdlet article.
    - In the New-AzureRmFrontDoorManagedRuleObject article, fixed the link to the New-AzureRmFrontDoorRuleGroupOverrideObject cmdlet article.

### Az.RecoveryServices

* Added client side validations for Azure File Share restore operations.
* Made storageAccountName and storageAccountResourceGroupName optional for afs restore.

### Az.Resources

* Fix for https://github.com/Azure/azure-powershell/issues/7679
    - Update Get-AzureRmRoleAssignment to use the subscription scope if it is provided when requesting classic administrators.

### Az.Sql

* Minor changes for upcoming AzureRM to Az transition
* Fixed issue with using Get-AzureRmSqlDatabaseVulnerabilityAssessment with DotNet core
* Modified documentation of help messages related to SQL Auditing cmdlets.

### Az.Storage

* Add -EnableHierarchicalNamespace to New-AzureRmStorageAccount
* Fix issue that Copy File cmdlet can't reuse source context in destination when not input -DestContext
    - Start-AzureStorageFileCopy
* Support Static Website configuration
    - Enable-AzureStorageStaticWebsite
    - Disable-AzureStorageStaticWebsite

### Az.Websites

* Set-AzureRmWebApp and Set-AzureRmWebAppSlot 
    - New parameter (-AzureStoragePath) added to specify Azure Storage paths to be mounted in Windows and Linux container apps. Use the output of the new cmdlet New-AzureRmWebAppAzureStoragePath as a parameter to set the Azure Storage paths.

## 0.6.1 - November 2018

### Az.ApiManagement
* Update dependencies for type mapping issue

### Az.Automation
* Swagger based Azure Automation cmdlets
* Added Update Management cmdlets
* Added Source Control cmdlets
* Added Remove-AzureRmAutomationHybridWorkerGroup cmdlet
* Fixed the DSC Register Node command

### Az.Compute
* Fixed identity issue for SystemAssigned identity
* Update dependencies for type mapping issue

### Az.ContainerInstance
* Update dependencies for type mapping issue

### Az.MarketplaceOrdering
* update the examples description for marketplace cmdlets

### Az.Network
* Added cmdlet New-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayCustomError, Get-AzureRmApplicationGatewayCustomError, Set-AzureRmApplicationGatewayCustomError, Remove-AzureRmApplicationGatewayCustomError, Add-AzureRmApplicationGatewayHttpListenerCustomError, Get-AzureRmApplicationGatewayHttpListenerCustomError, Set-AzureRmApplicationGatewayHttpListenerCustomError, Remove-AzureRmApplicationGatewayHttpListenerCustomError
* Added ICMP back to supported AzureFirewall Network Protocols
* Update cmdlet Test-AzureRmNetworkWatcherConnectivity, add validation on destination id, address and port. 
* Fix issues with memory usage in VirtualNetwork map

### Az.RecoveryServices.Backup
* Fix for modifying policy for a protected file share.
* Converted policy timezone to uppercase.

### Az.RecoveryServices.SiteRecovery
* Corrected example in New-AzureRmRecoveryServicesAsrProtectableItem
* Update dependencies for type mapping issue

### Az.Relay
* Added optional Parameter -KeyValue to New-AzureRmRelayKey cmdlet, which enables user to provide KeyValue.

### Az.Resources
* Update help documentation for resource identity related parameters in `New-AzureRmPolicyAssignment` and `Set-AzureRmPolicyAssignment`
* Add an example for New-AzureRmPolicyDefinition that uses -Metadata
* Fix to allow case preservation in Tag keys in NetStandard: #7678 #7703

### Az.ServiceFabric
* Add deprecation messages for upcoming breaking changes

### Az.Sql
* Added new cmdlets for CRUD operations on Azure Sql Database Managed Instance and Azure Sql Managed Database
	- Get-AzureRmSqlInstance
	- New-AzureRmSqlInstance
	- Set-AzureRmSqlInstance
	- Remove-AzureRmSqlInstance
	- Get-AzureRmSqlInstanceDatabase
	- New-AzureRmSqlInstanceDatabase
	- Restore-AzureRmSqlInstanceDatabase
	- Remove-AzureRmSqlInstanceDatabase
* Enabled Extended Auditing Policy management on a server or a database.
	- New parameter (PredicateExpression) was added to enable filtering of audit logs.
	- Cmdlets were modified to use SQL clients instead of Legacy clients.
	- Set-AzureRmSqlServerAuditing.
	- Get-AzureRmSqlServerAuditing.
	- Set-AzureRmSqlDatabaseAuditing.
	- Get-AzureRmSqlDatabaseAuditing.
* Fixed issue with using Update-AzureRmSqlDatabaseVulnerabilityAssessmentSettings with storage account name parameter set

## 0.5.0 - November 2018
#### General
* Added Resource Completers to many core cmdlets - these alloow you to tab through existing resource names when invoking cmdlets interactively

#### Az.Profile
* Update common code to use latest version of ClientRuntime
* Rename param TenantId in cmdlet Connect-AzAccount to Tenant and add an alias for TenantId
* Updated TenantId description for Connect-AzAccount
* Fix error message for failed login when providing tenant domain
    - https://github.com/Azure/azure-powershell/issues/6936
* Fix issue with context name clashing for accounts with no subscriptions in tenant
    - https://github.com/Azure/azure-powershell/issues/7453
* Fix issue with DataLake endpoints when using MSI
    - https://github.com/Azure/azure-powershell/issues/7462
* Fix issue where 'Disconnect-AzAccount' would throw if not connected
    - https://github.com/Azure/azure-powershell/issues/7167

#### Az.CognitiveServices
* Add Get-AzCognitiveServicesAccountSkus operation.

#### Az.Compute
* Add Add-AzVmssVMDataDisk and Remove-AzVmssVMDataDisk cmdlets
* Get-AzVMImage shows AutomaticOSUpgradeProperties
* Fixed SetAzVMChefExtension -BootstrapOptions and -JsonAttribute option values are not setting in json format.

#### Az.DataLakeStore
* Update the DataLake package to 1.1.10.
* Add default Concurrency to multithreaded operations.

#### Az.Insights
* Fixed issue #7267 (Autoscale area)
    - Issues with creating a new autoscale rule not properly setting enumerated parameters (would always set them to the default value).
* Fixed issue #7513 [Insights] Set-AzDiagnosticSetting requires explicit specification of categories during creation of setting
    - Now the cmdlet does not require explicit indication of the categories to enable during creation, i.e. it works as it is documented

#### Az.Network
* Changed PeeringType to be a mandatory parameter for the following cmdlets:-
    - Get-AzExpressRouteCircuitRouteTable
    - Get-AzExpressRouteCircuitARPTable
    - Get-AzExpressRouteCircuitRouteTableSummary
    - Get-AzExpressRouteCrossConnectionArpTable
    - Get-AzExpressRouteCrossConnectionRouteTable
    - Get-AzExpressRouteCrossConnectionRouteTableSummary

#### Az.PolicyInsights
* Added policy remediation cmdlets

#### Az.Resources
* Fix for https://github.com/Azure/azure-powershell/issues/7402
    - Allow listing resources using the '-ResourceId' parameter for 'Get-AzResource'

#### Az.ServiceBus
* Added MigrationState read-only property to PSServiceBusMigrationConfigurationAttributes which will help to know the Migration state.

#### Az.ServiceFabric
* Fix add certificate to Linux Vmss.
* Fix 'Add-AzServiceFabricClusterCertificate'
    - Using correct thumbprint from new certificate (Azure/service-fabric-issues#932).
    - Display exception correctly (Azure/service-fabric-issues#1054).
* Fix 'Update-AzServiceFabricDurability' to update cluster configuration before starting Vmss CreateOrUpdate operation.

## 0.4.0 - October 2018
#### Az.Profile
* Fix issue with Get-AzSubscription in CloudShell
* Update common code to use latest version of ClientRuntime

#### Az.Compute
* Added new sizes to the whitelist of VM sizes for which accelerated networking will be turned on when using the simple param set for 'New-AzVm'
* Added ResourceName argument completer to all cmdlets.

#### Az.DataLakeStore
* Adding support for Virtual Network Rules
    - Get-AzDataLakeStoreVirtualNetworkRule: Gets or Lists Azure Data Lake Store virtual network rule.
    - Add-AzDataLakeStoreVirtualNetworkRule: Adds a virtual network rule to the specified Data Lake Store account.
    - Set-AzDataLakeStoreVirtualNetworkRule: Modifies the specified virtual network rule in the specified Data Lake Store account.
    - Remove-AzDataLakeStoreVirtualNetworkRule: Deletes an Azure Data Lake Store virtual network rule.

#### Az.Network
* Update cmdlet Test-AzNetworkWatcherConnectivity, pass the protocol value to backend.
* Added ResourceName argument completer to all cmdlets.

#### Az.Resources
* Fix isssue where Get-AzRoleDefinition throws an unintelligible exception (when the default profile has no subscription in it and no scope is specified) by adding a meaningful exception in the scenario. Also set the default param set to 'RoleDefinitionNameParameterSet'.

## 0.3.0 - October 2018
#### Azure.Storage
* Fix Copy Blob/File won't copy metadata when destination has metadata issue
    - Start-AzureStorageBlobCopy
    - Start-AzureStorageFileCopy
* Support get the Storage resource usage of a specific location, and add warning message for get global Storage resource usage is obsolete.
    - Get-AzStorageUsage
    
#### Az.CognitiveServices
* Support Get-AzCognitiveServicesAccountSkus without an existing account.

#### Az.Compute
* Fix Get-AzVM -ResourceGroupName <rg> to return more than 50 results if needed
* Added an example of the 'SimpleParameterSet' to New-AzVmss cmdlet help.
* Fixed a typo in the Azure Disk Encryption progress message

#### Az.DataFactoryV2
* Updated the ADF .Net SDK version to 2.3.0.

#### Az.Network
* Added NetworkProfile functionality. new cmdlets added
    - Get-AzNetworkProfile
    - New-AzNetworkProfile
    - Remove-AzNetworkProfile
    - Set-AzNetworkProfile
    - New-AzContainerNicConfig
    - New-AzContainerNicConfigIpConfig
* Added service association link on Subnet Model
* Added cmdlet New-AzVirtualNetworkTap, Get-AzVirtualNetworkTap, Set-AzVirtualNetworkTap, Remove-AzVirtualNetworkTap
* Added cmdlet Set-AzNEtworkInterfaceTapConfig, Get-AzNEtworkInterfaceTapConfig, Remove-AzNEtworkInterfaceTapConfig

#### Az.RedisCache
* Allow any string as Size parameter going forward. Add P5 in PSArgumentCompleter popup

#### Az.Resources
* Add missing -Mode parameter to Set-AzPolicyDefinition
* Fix Get-AzProviderOperation commandlet bug for operations with Origin containing User

#### Az.Sql
* Fixed issue where some backup cmdlets would not recognize the current azure subscription

#### Az.Websites
* New Cmdlet Get-AzWebAppContainerContinuousDeploymentUrl - Gets the Container Continuous Deployment Webhook URL
* New Cmdlets New-AzWebAppContainerPSSession and Enter-WebAppContainerPSSession  - Initiates a PowerShell remote session into a windows container app

## 0.2.0 - September 2018
 Initial Release