Azure PowerShell 4.3.1 Installer: [link](https://github.com/Azure/azure-powershell/releases/download/v4.3.1-August2017/azure-powershell.4.3.1.msi)

Gallery Module for ARM Cmdlets: [link](https://www.powershellgallery.com/packages/AzureRM/4.3.1)

Gallery Module for Legacy Cmdlets for Service Management (RDFE): [link](https://www.powershellgallery.com/packages/Azure/4.3.1)

## Changes in 4.3.1

- Fixed issue with certain assemblies not being signed, resulting in an `could not load file or assembly` error when modules were imported

## Changes in 4.3.0

* AnalysisServices
    * Fixed bug in Set-AzureRmAnalysisServciesServer
        - When admin was not provided, the admin will be removed.
    * Added BackupBlobContainerUri in New-AzureRmAnalysisServicesServer and Set-AzureRmAnalysisServicesServer
        - Enable to set/disable backup blob container for backup/restore Azure Analysis Services Server
    * Updated Sku lookup in New-AzureRmAnalysisServicesServer and Set-AzureRmAnalysisServicesServer
        - Changed hard coded Sku into dynamic lookup.
    * Add-AzureAnalysisServicesAccount to support login with Service Principal
* Automation
    * Made changes to AutomationDSC* cmdlets to pull more than 100 records
    * Resolved the issue where the Verbose streams stop working after calling some Automation cmdlets (for example Get-AzureRmAutomationVariable, Get-AzureRmAutomationJob).
    * Support for NodeConfiguration Build versioning added in StartAzureAutomationDscCompilationJob and ImportAzureAutomationDscNodeConfiguration.
    * Bug fixes for existing issues - Fixes the alias issue is #3775 and the runOn alias and support for HybridWorkers.
* Compute
    * Set-AzureRmVMAEMExtension: Add support for new Premium Disk sizes
    * Set-AzureRmVMAEMExtension: Add support for M series
    * Add ForceUpdateTag parameter to Add-AzureRmVmssExtension
    * Add Primary parameter to New-AzureRmVmssIpConfig
    * Add EnableAcceleratedNetworking parameter to Add-AzureRmVmssNetworkInterfaceConfig
    * Add InstanceId to Set-AzureRmVmss
    * Expose MaintenanceRedeployStatus to Get-AzureRmVM -Status output
    * Expose Restriction and Capability to the table format of Get-AzureRmComputeResourceSku
* DataLakeStore
    * Fix for issue: https://github.com/Azure/azure-powershell/issues/4323
* EventHub
    * added ResourceGroup property to NamespaceAttributes
        - 'ResourceGroup' Gets the name of the resource group the Namespace is in
    * updated commandlets with new parameter and parameter alias
        - below cmdlets updated with Parametersets for Namespace and EventHub for operation of AuthorizationRule
        - New-AzureRmEventHubAuthorizationRule
            + Adds a new AuthorizationRule to the existing NameSpace or EventHub.
        - Get-AzureRmEventHubAuthorizationRule
            + Gets AuthorizationRule / List of AuthorizationRules for the existing NameSpace or EventHub.
        - Set-AzureRmEventHubAuthorizationRule
            + Updates properties of existing AuthorizationRule of EventHub NameSpace.
        - Remove-AzureRmEventHubAuthorizationRule
            + Deletes the existing AuthorizationRule of existing NameSpace or EventHub.
        - New-AzureRmEventHubKey
            + Generates a new Primary/Secondary Key for AuthorizationRule of existing NameSpace or EventHub.
        - Get-AzureRmEventHubKey
            + Gets Primary/Secondary Key for AuthorizationRule of existing NameSpace or EventHub.
* Network
    * New-AzureRmExpressRouteCircuitPeeringConfig: Added IPv6 support. New optional parameter added
    	- PeerAddressType
    * Set-AzureRmExpressRouteCircuitPeeringConfig: Added IPv6 support. New optional parameter added
    	- PeerAddressType
    * Remove-AzureRmExpressRouteCircuitPeeringConfig: Added IPv6 support. New optional parameter added
    	- PeerAddressType
    * Marked parameter -ProbeEnabled as obsolete
        - Add-AzureRmApplicationGatewayBackendHttpSettings
        - New-AzureRmApplicationGatewayBackendHttpSettings
        - Set-AzureRmApplicationGatewayBackendHttpSettings
* Profile
    * Data collection has been enabled by default. Usage data is collected by Microsoft in order to improve the user experience. The data is anonymous and does not include command-line argument values.
        - Use the Disable-AzureRmDataCollection cmdlet to turn the feature off
        - Use the Enable-AzureRmDataCollection cmdlet to turn this feature on
* Resources
    * Add Support for validation of scopes for the following roledefinition and roleassignment commandlets before sending the request to ARM
        - Get-AzureRMRoleAssignment
        - New-AzureRMRoleAssignment
        - Remove-AzureRMRoleAssignment
        - Get-AzureRMRoleDefinition
        - New-AzureRMRoleDefinition
        - Remove-AzureRMRoleDefinition
        - Set-AzureRMRoleDefinition
* ServiceBus
    * Added below new commandlets for AuthorizationRules for NameSpace, Queue and Topic. according to parameter set the authorization rule orperations are perfomed.
     - New-AzureRmServiceBusAuthorizationRule
       - Adds a new AuthorizationRule to the existing ServiceBus NameSpace/Queue/Topic.
     - Get-AzureRmServiceBusAuthorizationRule
       - Gets AuthorizationRule / List of AuthorizationRules for the existing ServiceBus NameSpace/Queue/Topic.
     - Set-AzureRmServiceBusAuthorizationRule
       - Updates properties of existing AuthorizationRule of Servicebus NameSpace/Queue/Topic.
     - New-AzureRmServiceBusKey
       - Generates a new Primary/Secondary Key for AuthorizationRule of existing ServiceBus NameSpace/Queue/Topic.
     - Get-AzureRmServiceBusKey
       - Gets Primary/Secondary Key for AuthorizationRule of existing ServiceBus NameSpace/Queue/Topic.
     - Remove-AzureRmServiceBusNamespaceAuthorizationRule
       - Deletes the existing AuthorizationRule of ServiceBus NameSpace/Queue/Topic.
    * Added Resource Group property to NamespceAttributes
* Sql
    * Updating Set-AzureRmSqlServerTransparentDataEncryptionProtector to display a warning and require confirmation if the Encryption Protector Type is being set to AzureKeyVault
    * Adding new updated cmdlets for Auditing settings
    	- Adding Get-AzureRmSqlDatabaseAuditing cmdlet which gets the auditing settings of an Azure SQL database.
    	- Adding Get-AzureRmSqlServerAuditing cmdlet which gets the auditing settings of an Azure SQL server.
    	- Adding Set-AzureRmSqlDatabaseAuditing cmdlet which changes the auditing settings for an Azure SQL database.
    	- Adding Set-AzureRmSqlServerAuditing cmdlet which changes the auditing settings of an Azure SQL server.
    * Deprecating the existing Auditing policy cmdlets
    	- Deprecating Get-AzureRmSqlDatabaseAuditingPolicy
    	- Deprecating Get-AzureRmSqlServerAuditingPolicy
    	- Deprecating Set-AzureRmSqlDatabaseAuditingPolicy
    	- Deprecating Set-AzureRmSqlServerAuditingPolicy
    	- Deprecating Use-AzureRmSqlServerAuditingPolicy
    	- Deprecating Remove-AzureRmSqlDatabaseAuditing
    	- Deprecating Remove-AzureRmSqlServerAuditing
    * Schema file parsing for Update-AzureRmSqlSyncGroup is now case insensitive.
* Storage
    * Add NeworkRule support to resource mode storage account cmdlets
        - New-AzureRmStorageAccount
        - Set-AzureRmStorageAccount
        - Get-AzureRmStorageAccountNetworkRuleSet
        - Update-AzureRmStorageAccountNetworkRuleSet
        - Add-AzureRmStorageAccountNetworkRule
        - Remove-AzureRmStorageAccountNetworkRule

View [changes since last release](https://github.com/Azure/azure-powershell/compare/v4.2.1-July2017...v4.3.1-August2017)
