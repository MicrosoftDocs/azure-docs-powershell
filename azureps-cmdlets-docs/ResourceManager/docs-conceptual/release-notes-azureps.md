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
ms.date: 05/18/2017
---

# Release notes

This is a list of changes made to Azure PowerShell in this release.

## Version 4.0.0

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
