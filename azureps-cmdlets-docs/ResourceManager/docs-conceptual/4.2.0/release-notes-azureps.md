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
ms.date: 07/26/2017
---

# Release notes

This is a list of changes made to Azure PowerShell in this release.

## 2017.07.17 - Version 4.2.1
* Compute
    - Fix issue with VM DIsk and VM Disk snapshot create and update cmdlets, (link)[https://github.com/azure/azure-powershell/issues/4309]
      - New-AzureRmDisk
      - New-AzureRmSnapshot
      - Update-AzureRmDisk
      - Update-AzureRmSnapshot
* Profile
    - Fix issue with non-interactive user authentication in RDFE (link)[https://github.com/Azure/azure-powershell/issues/4299]
* ServiceManagement
    - Fix issue with non-interactive user authentication (link)[https://github.com/Azure/azure-powershell/issues/4299]

## 2017.7.11 - Version 4.2.0
* AnalysisServices
    * Add new dataplane API
        - Introduced API to fetch AS server log, Export-AzureAnalysisServicesInstanceLog
* Automation
    * Properly setting TimeZone value for Weekly and Monthly schedules for New-AzureRmAutomationSchedule
        - More information can be found in this issue: https://github.com/Azure/azure-powershell/issues/3043
* AzureBatch
    - Added new Get-AzureBatchJobPreparationAndReleaseTaskStatus cmdlet.
    - Added byte range start and end to Get-AzureBatchNodeFileContent parameters.
* CognitiveServices
    * Integrate with Cognitive Services Management SDK version 1.0.0.
    * Fix an account name length checking bug.
* Compute
    * Storage account type support for Image disk:
        - 'StorageAccountType' parameter is added to Set-AzureRmImageOsDisk and Add-AzureRmImageDataDisk
    * PrivateIP and PublicIP feature in Vmss Ip Configuration:
        - 'PrivateIPAddressVersion', 'PublicIPAddressConfigurationName', 'PublicIPAddressConfigurationIdleTimeoutInMinutes', 'DnsSetting' names are added to New-AzureRmVmssIpConfig
        - 'PrivateIPAddressVersion' parameter for specifying IPv4 or IPv6 is added to New-AzureRmVmssIpConfig
    * Performance Maintenance feature:
        - 'PerformMaintenance' switch parameter is added to Restart-AzureRmVM.
        - Get-AzureRmVM -Status shows the information of performance maintenance of the given VM
    * Virtual Machine Identity feature:
        - 'IdentityType' parameter is added to New-AzureRmVMConfig and UpdateAzureRmVM
        - Get-AzureRmVM shows the information of the identity of the given VM
    * Vmss Identity feature:
        - 'IdentityType' parameter is added to to New-AzureRmVmssConfig
        - Get-AzureRmVmss shows the information of the identity of the given Vmss
    * Vmss Boot Diagnostics feature:
        - New cmdlet for setting boot diagnostics of Vmss object: Set-AzureRmVmssBootDiagnostics
        - 'BootDiagnostic' parameter is added to New-AzureRmVmssConfig
    * Vmss LicenseType feature:
        - 'LicenseType' parameter is added to New-AzureRmVmssConfig
    * RecoveryPolicyMode support:
        - 'RecoveryPolicyMode' paramter is added to New-AzureRmVmssConfig
    * Compute Resource Sku feature:
        - New cmdlet 'Get-AzureRmComputeResourceSku' list all compute resource skus
* DataFactories
    * Deprecate New-AzureRmDataFactoryGatewayKey
    * Introduce gateway auth key feature by adding New-AzureRmDataFactoryGatewayAuthKey and Get-AzureRmDataFactoryGatewayAuthKey
* DataLakeAnalytics
    * Add support for Compute Policy CRUD through the following commands:
        - New-AzureRMDataLakeAnalyticsComputePolicy
        - Get-AzureRMDataLakeAnalyticsComputePolicy
        - Remove-AzureRMDataLakeAnalyticsComputePolicy
        - Update-AzureRMDataLakeAnalyticsComputePolicy
    * Add support for job relationship metadata for help with recurring jobs and job pipelines. The following commands were updated or added:
        - Submit-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJob
        - Get-AzureRMDataLakeAnalyticsJobRecurrence
        - Get-AzureRMDataLakeAnalyticsJobPipeline
    * Updated the token audience for job and catalog APIs to use the correct Data Lake specific audience instead of the Azure Resource audience.
* DataLakeStore
    * Added support for user managed KeyVault key rotations in the Set-AzureRMDataLakeStoreAccount cmdlet
    * Added a quality of life update to automatically trigger an `enableKeyVault` call when a user managed KeyVault is added or a key is rotated.
    * Updated the token audience for job and catalog APIs to use the correct Data Lake specific audience instead of the Azure Resource audience.
    * Fixed a bug limiting the size of files created/appended using the following cmdlets:
        - New-AzureRmDataLakeStoreItem
        - Add-AzureRmDataLakeStoreItemContent
* Dns
    * Fix bug in the piping scenario for Get-AzureRmDnsZone
        - More information can be found here: https://github.com/Azure/azure-powershell/issues/4203
* HDInsight
    * Added support to enable / disable Operations Management Suite(OMS)
    * New cmdlets
        - Enable-AzureRmHDInsightOperationsManagementSuite
        - Disable-AzureRmHDInsightOperationsManagementSuite
        - Get-AzureRmHDInsightOperationsManagementSuite
    * Add new parameters to set Spark custom configurations to Add-AzureRmHDInsightConfigValues
        - Parameters SparkDefaults and SparkThriftConf for Spark 1.6
        - Parameters Spark2Defaults and Spark2ThriftConf for Spark 2.0
* Insights
    * Issue #4215 (change request) remove the 15 days limit in the time window for the Get-AzureRmLog cmdlet. Also minor changes to the unit test names.
    * Issue #3957 fixed for Get-AzureRmLog
        - Issue #1: The backend returns the records in pages of 200 records each, linked by the continuation token to the next page. The customers were seeing the cmdlet returning only 200 records when they knew there were more. This was happening regardless of the value they set for MaxEvents, unless that value was less than 200.
        - Issue #2: The documentation contained incorrect data about this cmdlet, e.g.: the default timewindow was 1 hour.
        - Fix #1: The cmdlet now follows the continuation token returned by the backend until it reaches MaxEvents or the end of the set.<br>The default value for MaxEvents is 1000 and its maximum is 100000. Any value for MaxEvents that is less than 1 is ignored and the default is used instead. These values and behavior did not change, now they are correctly documented.<br>An alias for MaxEvents has been added -MaxRecords- since the name of the cmdlet does not speak about events anymore, but only about Logs.
        - Fix #2: The documentation contains correct and more detailed information: new alias, correct time window, correct default, minimum, and maximum values.
* KeyVault
    * Remove email address from the directory query when -UserPrincipalName is specified to the Set-AzureRMKeyVaultAccessPolicy and Remove-AzureRMKeyVaultAccessPolicy cmdlets.
      - Both Cmdlets now have an -EmailAddress parameter that can be used instead of the -UserPrincipalName parameter when querying for email address is appropriate.  If there are more than one matching email addresses in the directory then the Cmdlet will fail.
* Network
    * New-AzureRmIpsecPolicy: SALifeTimeSeconds and SADataSizeKilobytes are no longer mandatory parameters
        - SALifeTimeSeconds defaults to 27000 seconds
        - SADataSizeKilobytes defaults to 102400000 KB
    * Added support for custom cipher suite configuration using ssl policy and listing all ssl options api in Application Gateway
        - Added optional parameter -PolicyType, -PolicyName, -MinProtocolVersion, -Ciphersuite
            - Add-AzureRmApplicationGatewaySslPolicy
            - New-AzureRmApplicationGatewaySslPolicy
            - Set-AzureRmApplicationGatewaySslPolicy
        - Added Get-AzureRmApplicationGatewayAvailableSslOptions (Alias: List-AzureRmApplicationGatewayAvailableSslOptions)
        - Added Get-AzureRmApplicationGatewaySslPredefinedPolicy (Alias: List-AzureRmApplicationGatewaySslPredefinedPolicy)
    * Added redirect support in Application Gateway
        - Added Add-AzureRmApplicationGatewayRedirectConfiguration
        - Added Get-AzureRmApplicationGatewayRedirectConfiguration
        - Added New-AzureRmApplicationGatewayRedirectConfiguration
        - Added Remove-AzureRmApplicationGatewayRedirectConfiguration
        - Added Set-AzureRmApplicationGatewayRedirectConfiguration
        - Added optional parameter -RedirectConfiguration
            - Add-AzureRmApplicationGatewayRequestRoutingRule
            - New-AzureRmApplicationGatewayRequestRoutingRule
            - Set-AzureRmApplicationGatewayRequestRoutingRule
        - Added optional parameter -DefaultRedirectConfiguration
            - Add-AzureRmApplicationGatewayUrlPathMapConfig
            - New-AzureRmApplicationGatewayUrlPathMapConfig
            - Set-AzureRmApplicationGatewayUrlPathMapConfig
        - Added optional parameter -RedirectConfiguration
            - Add-AzureRmApplicationGatewayPathRuleConfig
            - New-AzureRmApplicationGatewayPathRuleConfig
            - Set-AzureRmApplicationGatewayPathRuleConfig
        - Added optional parameter -RedirectConfigurations
            - New-AzureRmApplicationGateway
            - Set-AzureRmApplicationGateway
    * Added support for azure websites in Application Gateway
        - Added New-AzureRmApplicationGatewayProbeHealthResponseMatch
        - Added optional parameters -PickHostNameFromBackendHttpSettings, -MinServers, -Match
            - Add-AzureRmApplicationGatewayProbeConfig
            - New-AzureRmApplicationGatewayProbeConfig
            - Set-AzureRmApplicationGatewayProbeConfig
        - Added optional parameters -PickHostNameFromBackendAddress, -AffinityCookieName, -ProbeEnabled, -Path
            - Add-AzureRmApplicationGatewayBackendHttpSettings
            - New-AzureRmApplicationGatewayBackendHttpSettings
            - Set-AzureRmApplicationGatewayBackendHttpSettings
    * Update Get-AzureRmPublicIPaddress to retrieve publicipaddress resources created via VM Scale Set
    * Added cmdlet to get virtual network current usage
        - Get-AzureRmVirtualNetworkUsageList
* Profile
    * Fixed error when using Import-AzureRmContext or Save-AzureRmContext
        - More information can be found in this issue: https://github.com/Azure/azure-powershell/issues/3954
* RecoveryServices.SiteRecovery
    * Introducing a new module for Azure Site Recovery operations.
    	- All cmdlets begin with AzureRmRecoveryServicesAsr*
* Sql
    * Add Data Sync PowerShell Cmdlets to AzureRM.Sql
    * Updated AzureRmSqlServer cmdlets to use new REST API version that avoids timeouts when creating server.
    * Deprecated server upgrade cmdlets because the old server version (2.0) no longer exists.
    * Add new optional switch paramter "AssignIdentity" to New-AzureRmSqlServer and Set-AzureRmSqlServer cmdlets to support provisioning of a resource identity for the SQL server resource
    * The parameter ResourceGroupName is now optional for Get-AzureRmSqlServer
    	- More information can be found in the following issue: https://github.com/Azure/azure-powershell/issues/635
* ServiceManagement
    For ExpressRoute:
    * Updated New-AzureBgpPeering cmdlet to add following new options :
        - PeerAddressType : Values of "IPv4" or "IPv6" can be specified to create a BGP Peering of the corresponding address family type
    * Updated Set-AzureBgpPeering cmdlet to add following new options :
        - PeerAddressType : Values of "IPv4" or "IPv6" can be specified to update BGP Peering of the corresponding address family type
    * Updated Remove-AzureBgpPeering cmdlet to add following new options :
        - PeerAddressType : Values of "IPv4", "IPv6" or All can be specified to remove BGP Peering of the corresponding address family type or all of them

## 2017.06.07 - Version 4.1.0
* AnalysisServices
    * New SKUs added: B1, B2, S0
    * Scale up/down support added
* CognitiveServices
    * Update detailed display of license agreements when creating Cognitive Services resources
* Compute
    * Fix Test-AzureRmVMAEMExtension for virtual machines with multiple managed disks
    * Updated Set-AzureRmVMAEMExtension: Add caching information for Premium managed disks
    * Add-AzureRmVhd: The size limit on vhd is increased to 4TB.
    * Stop-AzureRmVM: Clarify documentation for STayProvisioned parameter
    * New-AzureRmDiskUpdateConfig
      * Deprecated parameters CreateOption, StorageAccountId, ImageReference, SourceUri, SourceResourceId
    * Set-AzureRmDiskUpdateImageReference: Deprecated cmdlet
    * New-AzureRmSnapshotUpdateConfig
      * Deprecated parameters CreateOption, StorageAccountId, ImageReference, SourceUri, SourceResourceId
    * Set-AzureRmSnapshotUpdateImageReference: Deprecated Cmdlet
* DataLakeStore
    * Enable-AzureRmDataLakeStoreKeyVault (Enable-AdlStoreKeyVault)
      * Enable KeyVault managed encryption for a DataLake Store
* DevTestLabs
    * Update cmdlets to work with current and updated DevTest Labs API version.
* IotHub
    * Add Routing support for IoTHub cmdlets
* KeyVault
  * New Cmdlets to support KeyVault Managed Storage Account Keys
    * Get-AzureKeyVaultManagedStorageAccount
    * Add-AzureKeyVaultManagedStorageAccount
    * Remove-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccount
    * Update-AzureKeyVaultManagedStorageAccountKey
    * Get-AzureKeyVaultManagedStorageSasDefinition
    * Set-AzureKeyVaultManagedStorageSasDefinition
    * Remove-AzureKeyVaultManagedStorageSasDefinition
* Network
    * Get-AzureRmNetworkUsage: New cmdlet to show network usage and capacity details
    * Added new GatewaySku options for VirtualNetworkGateways
        * VpnGw1, VpnGw2, VpnGw3 are the new Skus added for Vpn gateways
    * Set-AzureRmNetworkWatcherConfigFlowLog
      * Fixed  help examples
* NotificationHubs
    * Transparent Update to NotificationHubs cmdlets for new API
* Profile
    * Resolve-AzureRmError
      * New cmdlet to show details of errors and exceptions thrown by cmdlets, including server request/response data
    * Send-Feedback
      * Enabled sending feedback without logging in
    * Get-AzureRmSubscription
      * Fix bug in retreiving CSP subscriptions
* Resources
    * Fixed issue where Get-AzureRMRoleAssignment would result in a Bad Request if the number of roleassignments where greater than 1000
        * Users can now use Get-AzureRMRoleAssignment even if the roleassignments to be returned is greater than 1000
* Sql
    * Restore-AzureRmSqlDatabase: Update documentation example
* Storage
    * Add AssignIdentity setting support to resource mode storage account cmdlets
        * New-AzureRmStorageAccount
        * Set-AzureRmStorageAccount
    * Add Customer Key Support to resource mode storage account cmdlets
        * Set-AzureRmStorageAccount
        * New-AzureRmStorageAccountEncryptionKeySource
* TrafficManager

    * New Monitor settings 'MonitorIntervalInSeconds', 'MonitorTimeoutInSeconds', 'MonitorToleratedNumberOfFailures'
    * New Monitor protocol 'TCP'
* ServiceManagement
    * Add-AzureVhd: The size limit on vhd is increased to 4TB.
    * New-AzureBGPPeering: Support LegacyMode
* Azure.Storage
    * Update help for parameters that accept wildcard characters and update StorageContext type

## 2017.05.23 - Version 4.0.2
* Profile
    * Add-AzureRmAccount
      * Added `-EnvironmentName` parameter alis for backward compatibility with 2.x versions of AzureRM.profile

## 2017.05.12 - Version 4.0.1
 * Fix issue with New-AzureStorageContext in offline scenarios: https://github.com/Azure/azure-powershell/issues/3939

## 2017.05.10 - Version 4.0.0


* This release contains breaking changes. Please see [the migration guide](https://aka.ms/azps-migration-guide) for change details and the impact on existing scripts.
* ApiManagement
  - Added support for configuring external groups in New-AzureRmApiManagementGroup.
* Billing
  - New Cmdlet Get-AzureRmBillingPeriod
    + cmdlet to retrieve azure billing periods of the subscription.
  - Update Cmdlet Get-AzureRmBillingInvoice
  - new property BillingPeriodNames
  - output in list view
* Compute
  - Updated Set-AzureRmVMAEMExtension and Test-AzureRmVMAEMExtension cmdlets to support Premium managed disks
  - Backup encryption settings for IaaS VMs and restore on failure
  - ChefServiceInterval option is renamed to ChefDaemonInterval now. Old one will continue to work however.
  - Remove duplicated DataDiskNames and NetworkInterfaceIDs properties from PS VM object.
  - Make DataDiskNames and NetworkInterfaceIDs parameters optional in Remove-AzureRmVMDataDisk and Remove-AzureRmVMNetworkInterface, respectively.
  - Fix the piping issue of Get cmdlets when the Get cmdlets return a list object.
  - Cmdlets that conflicted with RDFE cmdlets have been renamed. See issue https://github.com/Azure/azure-powershell/issues/2917 for more details
    + `New-AzureVMSqlServerAutoBackupConfig` has been renamed to `New-AzureRmVMSqlServerAutoBackupConfig`
    + `New-AzureVMSqlServerAutoPatchingConfig` has been renamed to `New-AzureRmVMSqlServerAutoPatchingConfig`
    + `New-AzureVMSqlServerKeyVaultCredentialConfig` has been renamed to `New-AzureRmVMSqlServerKeyVaultCredentialConfig`
* Consumption
  - New Cmdlet Get-AzureRmConsumptionUsageDetail
    + cmdlet to retrieve usage details of the subscription.
* ContainerRegistry
  - Add PowerShell cmdlets for Azure Container Registry
    + New-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistry
    + Update-AzureRmContainerRegistry
    + Remove-AzureRmContainerRegistry
    + Get-AzureRmContainerRegistryCredential
    + Update-AzureRmContainerRegistryCredential
    + Test-AzureRmContainerRegistryNameAvailability
* DataLakeAnalytics
  - Add support for catalog package get and list
  - Add support for listing the following catalog items from deeper ancestors:
    + Table
    + TVF
    + View
    + Statistics
* DataLakeStore
  - For `Import-AzureRMDataLakeStoreItem` and `Export-AzureRMDataLakeStoreItem` trace logging has been disabled by default to improve performance. If trace logging is desired please use the `-DiagnosticLogLevel` and `-DiagnosticLogPath` parameters
  - Fixed a bug that would sometimes cause PowerShell to crash when uploading lots of small file to ADLS.
* EventHub
  - Bug fix :
    + Fix for Set-AzureRmEventHubNamespace cmdlet error  - 'Tier' cannot be null, where it should be 'SkuName'
    + Set-AzureRmEventHub - Fix 'Object reference not set to an instance of an object' error while updating EventHub
* Insights
  - Add-AzureRm*AlertRule
    + Returns a single object: newResource, statusCode, requestId
  - Get-AzureRmAlertRule
    + The output is now enumerated instead of considered a single object. Its type did not change, it is still a list.
  - Remove-AzureRmAlertRule
    + The statusCode follows the status code returned by the request, before it was Ok always.
  - Add-AzureRmAutoscaleSetting
    + Returns now a single object (not a list as before) containing statusCode, requestId, and the newly created/updated resource.
    + The status code follows the status returned by the request, before it was always Ok.
  - New-AzureRmAutoscaleRule
    + The parameter ScaleActionType has been extended, it receives the following values now: ChangeCount, PercentChangeCount, ExactCount.
  - Remove-AzureRmAutoscaleSetting
    + The statusCode in the output follows the statusCode returned by the request. Before it was always Ok.
  - Get-AzureRMLogProfile
    + The output is now enumerated. Before it was considered a single object. The type of the output remains a list as before.
  - Remove-AzureRmLogProfile
    + The PassThru parameter has been implemented.
  - Metrics API
    + The SDK now retrieves metrics from MDM.
  - Get-AzureRmMetricDefinition
    + The output is still a list, but the structure of the list changed.
  - Get-AzureRmMetric
    + The call has changed. This is the new syntax: Get-AzureRmMetric ResourceId [MetricNames [TimeGrain] [AggregationType] [StartTime] [EndTime]] [DetailedOutput]
    + The output is a list, and the structure of its elements has changed.
* KeyVault
  - Adding backup/restore support for KeyVault secrets
    + Secrets can be backed up and restored, matching the functionality currently supported for Keys

  - Backup cmdlets for Keys and Secrets now accept a corresponding object as an input parameter
    + The caller may chain retrieval and backup operations: Get-AzureKeyVaultKey -VaultName myVault -Name myKey | Backup-AzureKeyVaultKey

  - Backup cmdlets now support a -Force switch to overwrite an existing file
    + Note that attempting to overwrite an existing file will no longer throw, and will instead prompt the user for a choice on how to proceed.
* LogicApp
  - New parameters for Interchange Control Number disaster recovery cmdlets:
    + Optional -AgreementType parameter ("X12", or "Edifact") to specify the relevant control numbers
* MachineLearning
  - Consume new version of Azure Machine Learning .Net SDK and add a new cmdlet
    + Add-AzureRmMlWebServiceRegionalProperty
  - Minor wording fixes in help text.
* Network
  - Added Test-AzureRmNetworkWatcherConnectivity cmdlet
    + Returns connectivity information for a specified source VM and a destination
    + If connectivity between the source and destination cannot be established, the cmdlet returns details about the issue
* Profile
  - Added `Send-Feedback' cmdlet: allows a user to initiate a set of prompts which sends feedback to the Azure PowerShell team.
  - The following aliases have been removed as they conflicted with existing cmdlet names in the Azure module:
    + `Enable-AzureDataCollection` (supported by `Enable-AzureRmDataCollection`)
    + `Disable-AzureDataCollection` (supported by `Disable-AzureRmDataCollection`)
* Relay
  - Adds cmdlets for the Azure Relay which allows users to create and manage all Azure Relay resources.
    + `New-AzureRmRelayNamespace`
    + `Get-AzureRmRelayNamespace`
    + `Set-AzureRmRelayNamespace`
    + `Remove-AzureRmRelayNamespace`
    + `New-AzureRmWcfRelay`
    + `Get-AzureRmWcfRelay`
    + `Set-AzureRmWcfRelay`
    + `Remove-AzureRmWcfRelay`
    + `New-AzureRmRelayHybridConnection`
    + `Get-AzureRmRelayHybridConnection`
    + `Set-AzureRmRelayHybridConnection`
    + `Remove-AzureRmRelayHybridConnection`
    + `Test-AzureRmRelayName`
    + `Get-AzureRmRelayOperation`
    + `New-AzureRmRelayKey`
    + `Get-AzureRmRelayKey`
    + `New-AzureRmRelayAuthorizationRule`
    + `Get-AzureRmRelayAuthorizationRule`
    + `Set-AzureRmRelayAuthorizationRule`
    + `Remove-AzureRmRelayAuthorizationRule`
* Resources
  - Support cross-resource-group deployments for New-AzureRmResourceGroupDeployment
    + Users can now use nested deployments to deploy to different resource groups.
* ServiceBus

  - Bug Fix: ServiceBus Queue object property values were set to null, the object is used as input parameter in Set-AzureRmServiceBusQueue cmdlet to update Queue.
   - Properties affected are LockDuration, EntityAvailabilityStatus, DuplicateDetectionHistoryTimeWindow, MaxDeliveryCount and MessageCount
* ServiceFabric

  - Added cmdlets for service fabric
    + Add-AzureRmServiceFabricApplicationCertificate
            Add a certificate which will be used as application certificate
    + Add-AzureRmServiceFabricClientCertificate
            Add a common name or thumbprint to the cluster settings for client authentication
    + Add-AzureRmServiceFabricClusterCertificate
            Add a secondary cluster certificate to the cluster for rolling over the existing certificate
    + Add-AzureRmServiceFabricNodes
            Add nodes/VMs of a specific node type to a cluster
    + Add-AzureRmServiceFabricNodeType
            Add a node type/VMs to an existing cluster
    + Get-AzureRmServiceFabricCluster
            Get the details of the cluster resource
    + New-AzureRmServiceFabricCluster
            Create a new ServiceFabric cluster. This command has many overloads to cover various scenarios
    + Remove-AzureRmServiceFabricClientCertificate
            Remove a client certificate from being used to access a cluster
    + Remove-AzureRmServiceFabricClusterCertificate
            Remove a cluster certificate from being used for cluster security
    + Remove-AzureRmServiceFabricNodes
            Remove nodes from a specific node type from a cluster
    + Remove-AzureRmServiceFabricNodeType
            Remove a node type from a cluster
    + Remove-AzureRmServiceFabricSettings
            Remove one or more ServiceFabric settings from a cluster
    + Set-AzureRmServiceFabricSettings
            Add or update one or more ServiceFabric settings of a cluster
    + Set-AzureRmServiceFabricUpgradeType
            Change the ServiceFabric upgrade type of a cluster
    + Update-AzureRmServiceFabricDurability
            Change the durability tier of a cluster
    + Update-AzureRmServiceFabricReliability
            Change the reliability tier of a cluster
* Sql
  - Added -SampleName parameter to New-AzureRmSqlDatabase
  - Updates to Failover Group cmdlets
  - Remove 'Tag' parameters
  - Remove 'PartnerResourceGroupName' and 'PartnerServerName' parameters from Remove-AzureRmSqlDatabaseFailoverGroup cmdlet
  - Add 'GracePeriodWithDataLossHours' parameter to New- and Set- cmdlets, which shall eventually replace 'GracePeriodWithDataLossHour'
  - Documentation has been fleshed out and updated
  - Change formatting of returned objects and fix some bugs where fields were not always populated
  - Add 'DatabaseNames' and 'PartnerLocation' properties to Failover Group object
  - Fix bug causing Switch- cmdlet to return immediately rather than waiting for operation to complete
  - Fix integer overflow bug when high grace period values are used
  - Adjust grace period to a minimum of 1 hour if a lower one is provided
  - Remove "Usage_Anomaly" from the accepted values for "ExcludedDetectionType" parameter of Set-AzureRmSqlDatabaseThreatDetectionPolicy cmdlet and Set-AzureRmSqlServerThreatDetectionPolicy cmdlet.
* Storage
  - Upgrade SRP SDK to 6.3.0
  - New/Set-AzureRmStorageAccount:Add a new parameter to support EnableHttpsTrafficOnly
  - New/Set/Get-AzureRmStorageAccount: Returned Storage Account contains a new attribute EnableHttpsTrafficOnly
* Azure.Storage
  - Upgrade to Azure Storage Client Library 8.1.1 and Azure Storage DataMovement Library 0.5.1
  - Add a new cmdlet to support blob Incremental Copy feature
