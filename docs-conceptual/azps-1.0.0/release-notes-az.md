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