---
title: Azure PowerShell Change Log | Microsoft Docs
description: This is a history of changes made to Azure PowerShell in the latest release.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.service: azure-resource-manager
ms.product: azure
ms.devlang: powershell
ms.topic: conceptual
ms.workload:
ms.date: 03/30/2017
---

# Release notes

This is a list of changes made to Azure PowerShell in the latest releases.

## Version 3.7.0

* ApiManagement
    * Added new cmdlets to manage Backend entity
        - New-AzureRmApiManagementBackend
        - Get-AzureRmApiManagementBackend
        - Set-AzureRmApiManagementBackend
        - Remove-AzureRmApiManagementBackend
    * Created supporting cmdlets to create in-memory objects required while Creating or Updating Backend entity
        - New-AzureRmApiManagementBackendCredential
        - New-AzureRmApiManagementBackendProxy
* Billing
    * New Cmdlet Get-AzureRmBillingInvoice
        - cmdlet to retrieve azure billing invoices of the subscription.
* Compute
    * Updated Set-AzureRmVMAEMExtension and Test-AzureRmVMAEMExtension cmdlets to support managed disks
* LogicApp
    * New cmdlets for X12 Interchange Control Number disaster recovery:
        - Get-AzureRmIntegrationAccountGeneratedIcn
        - Get-AzureRmIntegrationAccountReceivedIcn
        - Remove-AzureRmIntegrationAccountReceivedIcn
        - Set-AzureRmIntegrationAccountGeneratedIcn
        - Set-AzureRmIntegrationAccountReceivedIcn
* Network
    * Added support for connection draining to Application Gateways
        - Added Get-AzureRmApplicationGatewayConnectionDraining
        - Added New-AzureRmApplicationGatewayConnectionDraining
        - Added Remove-AzureRmApplicationGatewayConnectionDraining
        - Added Set-AzureRmApplicationGatewayConnectionDraining
        - Updated Add-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining
        - Updated New-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining
        - Updated Set-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining

    * Remapped unused 'Name' parameter in ExpressRoute cmdlets to 'ExpressRouteCircuitName'
        - Get-AzureRmExpressRouteCircuitARPTable
        - Get-AzureRmExpressRouteCircuitRouteTable
        - Get-AzureRmExpressRouteCircuitRouteTableSummary
        - Get-AzureRmExpressRouteCircuitStats
* Sql
    * Bug fix - Auditing and Threat Detection cmdlets now return a meaningfully error instead of null reference error.
    * Updating Transparent Data Encryption (TDE) with Bring Your Own Key (BYOK) support cmdlets for updated API.
* Websites
    * Update help documentation for AppServicePlan cmdlets
* ServiceManagement
    * Update the output object of migration cmdlets (Move-AzureService, Move-AzureStorageAccount, Move-AzureVirtualNetwork, Move-AzureNetworkSecurityGroup, Move-AzureReservedIP, Move-AzureRouteTable):
        - ValidationMessages contain "Information" and "Warning" messages in addition to "Error" messages.
        - Result output is changed according to ValidationMessages.

    * Removed ManagedCache cmdlets.  These cmdlets were non-functional and have been deprecated for more than a year
        - Get-AzureManagedCacheLocation
        - Get-AzureManagedCache
        - Get-AzureManagedCacheAccessKey
        - Get-AzureManagedCacheNamedCache
        - New-AzureManagedCache
        - New-AzureManagedCacheAccessKey
        - New-AzureManagedCacheNamedCache
        - Remove-AzureManagedCache
        - Remove-AzureManagedCacheNamedCache
        - Set-AzureManagedCache
        - Set-AzureManagedCacheNamedCache

## Version 2.2.0
* Compute
  * Add support for querying encryption status from the AzureDiskEncryptionForLinux extension
* DataFactory
  * Added new cmdlet for listing activity windows
    - Get-AzureRmDataFactoryActivityWindow
* DataLake
  * Changed parameter `Host` to `DatabaseHost` and added alias to `Host`
    - New-AzureRmDataLakeAnalyticsCatalogSecret
    - Set-AzureRmDataLakeAnalyticsCatalogSecret
  * Add support for ACL and Default ACL removal
  * Add support for getting and setting unnamed permissions on files and folders
* KeyVault
  * Add support for certificates
    - Add-AzureKeyVaultCertificate
    - Add-AzureKeyVaultCertificateContact
    - Get-AzureKeyVaultCertificate
    - Get-AzureKeyVaultCertificateContact
    - Get-AzureKeyVaultCertificateIssuer
    - Get-AzureKeyVaultCertificateOperation
    - Get-AzureKeyVaultCertificatePolicy
    - Import-AzureKeyVaultCertificate
    - New-AzureKeyVaultCertificateAdministratorDetails
    - New-AzureKeyVaultCertificateOrganizationDetails
    - New-AzureKeyVaultCertificatePolicy
    - Remove-AzureKeyVaultCertificate
    - Remove-AzureKeyVaultCertificateContact
    - Remove-AzureKeyVaultCertificateIssuer
    - Remove-AzureKeyVaultCertificateOperation
    - Set-AzureKeyVaultCertificateAttribute
    - Set-AzureKeyVaultCertificateIssuer
    - Set-AzureKeyVaultCertificatePolicy
    - Stop-AzureKeyVaultCertificateOperation
* Network

  * New switch parameter added for network interface to enable/disable accelerated networking
    -New-AzureRmNetworkInterface -EnableAcceleratedNetworking
  * Enable Active-Active gateway feature PowerShell cmdlets
    - Add-AzureRmVirtualNetworkGatewayIpConfig
    - Remove-AzureRmVirtualNetworkGatewayIpConfig
  * Added new cmdlet
    - Test-AzureRmPrivateIpAddressAvailability
* Resources
  * Support zones in provider and resource cmdlets
    - Get-AzureRmProvider
    - New-AzureRmResource
    - Set-AzureRmResource
* Sql
  * Added new cmdlets for Azure SQL threat detection policy management at server level
    - Get-AzureRmSqlServerThreatDetectionPolicy
    - Remove-AzureRmSqlServerThreatDetectionPolicy
    - Set-AzureRmSqlServerThreatDetectionPolicy
  * Added new cmdlets to support enabling/disabling GeoBackupPolicy for Sql Azure DataWarehouses
    - Get-AzureRmSqlDatabaseGeoBackupPolicy
    - Set-AzureRmSqlDatabaseGeoBackupPolicy
  * Added new cmdlets for Azure Sql Advisors and Recommended Actions APIs
    - Get-AzureRmSqlDatabaseAdvisor
    - Get-AzureRmSqlElasticPoolAdvisor
    - Get-AzureRmSqlServerAdvisor
    - Get-AzureRmSqlDatabaseRecommendedActions
    - Get-AzureRmSqlElasticPoolRecommendedActions
    - Get-AzureRmSqlServerRecommendedActions
    - Set-AzureRmSqlDatabaseAdvisorAutoExecuteStatus
    - Set-AzureRmSqlElasticPoolAdvisorAutoExecuteStatus
    - Set-AzureRmSqlServerAdvisorAutoExecuteStatus
    - Set-AzureRmSqlDatabaseRecommendedActionState
    - Set-AzureRmSqlElasticPoolRecommendedActionState
    - Set-AzureRmSqlServerRecommendedActionState

## Version 1.7.0
* **Behavioral change for -Force, –Confirm and $ConfirmPreference parameters for all cmdlets. We are changing this implementation to be in line with PowerShell guidelines. For most cmdlets, this means removing the Force parameter and to skip the ShouldProcess prompt, users will need to include the parameter: ‘-Confirm:$false’ in their PowerShell scripts.** This changes are addressing following issues:
  * Correct implementation of –WhatIf functionality, allowing a user to determine the effects of a cmdlet or script without making any actual changes
  * Control over prompting using a session-wide $ConfirmPreference, so that the user is prompted based on the impact of a prospective change (as reported in the ConfirmImpact setting in the cmdlet)
  * Cmdlet-specific control over confirmation prompts using the –Confirm parameter
  * Consistent use of ShouldContinue and the –Force parameter across cmdlets, for only those actions that would require prompting from the user due to the special nature of the changes (for example, deleting hidden files)
  * Consistency with other PowerShell cmdlets, so that PowerShell scripting knowledge from other cmdlets is immediately applicable to the Azure PowerShell cmdlets.

**Notice that now to *automatically skip all Prompts in all Circumstances* Azure PowerShell cmdlets require the user to supply two parameters:**
```powershell
My-CmdletWithConfirmation –Confirm:$false -Force
```
* Azure Compute
  * Set-AzureRmVMADDomainExtension
  * Get-AzureRmVMADDomainExtension
  * -Redeploy parameter for Restart-AzureVM
  * -Validate parameter for Move-AzureService, Move-AzureStorageAccount, and Move-AzureVirtualNetwork
  * Name and version parameters for extension cmdlets are optional as before.
  * New-AzureVM can get a license type from VM object.
* Azure Storage
  * Change Tags Parameter to Tag, and add parameter alias Tags
    - New-AzureRmStorageAccount
    - Set-AzureRmStorageAccount
* Azure Network
  * New cmdlet added for Virtual Network Peering
* Azure Redis Cache
  * New cmdlet added for Reset-AzureRmRedisCache
  * New cmdlet added for Export-AzureRmRedisCache
  * New cmdlet added for Import-AzureRmRedisCache
  * Modified cmdlet New-AzureRmRedisCache to include parameter change for vNet
* Azure SQL DB Backup/Restore
  * Cmdlets for LTR (Long Term Retention) backup feature
    * Get-AzureRmSqlServerBackupLongTermRetentionVault
    * Get-AzureRmSqlDatabaseBackupLongTermRetentionPolicy
    * Set-AzureRmSqlServerBackupLongTermRetentionVault
    * Set-AzureRmSqlDatabaseBackupLongTermRetentionPolicy
  * Restore-AzureRmSqlDatabase now supports point-in-time restore of a deleted database
  * Restore-AzureRmSqlDatabase now supports restoring from a Long Term Retention backup
* Azure LogicApp
  * Added LogicApp Integration accounts cmdlets.
    * Get-AzureRmIntegrationAccountAgreement
    * Get-AzureRmIntegrationAccountCallbackUrl
    * Get-AzureRmIntegrationAccountCertificate
    * Get-AzureRmIntegrationAccount
    * Get-AzureRmIntegrationAccountMap
    * Get-AzureRmIntegrationAccountPartner
    * Get-AzureRmIntegrationAccountSchema
    * New-AzureRmIntegrationAccountAgreement
    * New-AzureRmIntegrationAccountCertificate
    * New-AzureRmIntegrationAccount
    * New-AzureRmIntegrationAccountMap
    * New-AzureRmIntegrationAccountPartner
    * New-AzureRmIntegrationAccountSchema
    * Remove-AzureRmIntegrationAccountAgreement
    * Remove-AzureRmIntegrationAccountCertificate
    * Remove-AzureRmIntegrationAccount
    * Remove-AzureRmIntegrationAccountMap
    * Remove-AzureRmIntegrationAccountPartner
    * Remove-AzureRmIntegrationAccountSchema
    * Set-AzureRmIntegrationAccountAgreement
    * Set-AzureRmIntegrationAccountCertificate
    * Set-AzureRmIntegrationAccount
    * Set-AzureRmIntegrationAccountMap
    * Set-AzureRmIntegrationAccountPartner
    * Set-AzureRmIntegrationAccountSchema
* Azure Data Lake Store
  * Drastically improve performance of file and folder upload and download.
    * This includes a slight change to the parameter names for download and inclusion of two new parameters for upload:
      * NumThreads -> PerFileThreadCount, used to indicate the number of threads to use in a single file
      * ConcurrentFileCount, used to indicate the number of files to upload/download in parallel for folder upload/download.
    * Default threading values are now designed to give a better all around throughput for most file sizes. If performance is not as desired, the values above can be modified to meet requirements.
* Azure Data Lake Analytics
  * Get-AzureRMDataLakeAnalyticsDataSource now returns all data sources when called with no arguments.
    * This change also removes the data source type parameter from the cmdlet.
    * This change results in a new object being returned for the list operation with the following properties:
      * Type, the type of data source
      * Name, the name of the data source
      * IsDefault, set to true if this is the default data source for the account
  * Get-AzureRMDataLakeAnalyticsJob fixed for list for certain date time offset values when filtering on submittedBefore and submittedAfter.
* Web Apps
  * Add Swap-AzureRmWebAppSlot cmdlet for regular swap and swap with preview
  * Extend Set-AzureRmWebAppSlot cmdlet to support auto swap
* Azure API Management
  * Fixed Azure Api Management Deployment cmdlets for AzureChinaCloud.
  * Removed cmdlet Set-AzureRmApiManagementTenantGitAccess as Git Access is enabled by Default.
* Azure Recovery Services Backup
  * Added support for the Azure SQL workload
  * Added support for backing up and restoring encrypted Azure VMs
  * Backup-AzureRmRecoveryServicesBackupItem - Added optional retention time feature for recovery points
  * Minor filter-related bug fixes in Get-AzureRmRecoveryServicesBackupContainer and Get-AzureRmRecoveryServicesBackupItem cmdlets
* Azure Automation
  * Added Get-AzureRmAutomationHybridWorkerGroup

## Version 1.2.9

Changes This Release

* AzureRm.AzureStackAdmin Module
    - Changes in the Add-AzureRmResourceProviderRegistration cmdlet for the support of Admin Azure
      resource manager and tenant azure resource manager split. A new parameter -ResourceManagerType
      has been added.
    - Removal of the parameters -AdminUri, -ApiVersion, -SubscriptionId and -Token from each
      cmdlets. We have been printing warnings that these parameters will be deprecated and now they
      got removed.
* AzureStackStorage module
    - Added new cmdlets to support container migration scenarios.
    - Removed cmdlets referring to internal components and underlying features.
* AzureRM.BootStrapper
    - Created new module to manage versions of Azure PowerShell cmdlets through the use of version
      profiles