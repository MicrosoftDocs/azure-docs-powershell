## 2.4.0 - July 2019
#### Az.Accounts
* Add support for profile cmdlets
* Add support for environments and data planes in generated cmdlets
* Fix bug where incorrect endpoint was being used in some cases for data plane cmdlets in Windows PowerShell

#### Az.Advisor
* GA release of Az.Advisor
* This module is now included as a part of the roll-up `Az` module

#### Az.ApiManagement
* Fix for issue https://github.com/Azure/azure-powershell/issues/8671
    - **Get-AzApiManagementSubscription**
        - Added support for querying subscriptions by User and Product
        - Added support for querying using Scope '/', '/apis', '/apis/echo-api'
* Fix for issue https://github.com/Azure/azure-powershell/issues/9307 and https://github.com/Azure/azure-powershell/issues/8432
    - **Import-AzApiManagementApi**
        - Added support for specifying 'ApiVersion' and 'ApiVersionSetId' when importing Apis

#### Az.Automation
* Fixed Set-AzAutomationConnectionFieldValue cmdlet bug to handle string value.

#### Az.Compute
* Add HyperVGeneration parameter to New-AzImageConfig

#### Az.DataFactory
* Updating the output of get activity runs, get pipeline runs, and get trigger runs ADF cmdlets to support Select-Object pipe.

#### Az.EventGrid
* Fix typo in 'New-AzEventGridSubscription' documentation

#### Az.IotHub
* Add support to regenerate authorization policy keys.

#### Az.Network
* Added 'RoutingPreference' to public ip tags
* Improve examples for 'Get-AzNetworkServiceTag' reference documentation

#### Az.PolicyInsights
* Fix null reference issue in Get-AzPolicyState
    - More information here: https://github.com/Azure/azure-powershell/issues/9446

#### Az.OperationalInsights
* Fixed CustomLog datasource model returned in Get-AzOperationalInsightsDataSource

#### Az.RecoveryServices
* Fix for get-policy command for IaaSVMs

#### Az.Resources
    - Fix help text for Get-AzPolicyState -Top parameter
    - Add client-side paging support for Get-AzPolicyAlias
    - Add new parameters for Set-AzPolicyAssignment, -PolicyParameters and -PolicyParametersObject
    - Handful of doc and example updates for Policy cmdlets

#### Az.ServiceBus
* Fix for issue #4938 - New-AzureRmServiceBusQueue returns BadRequest when setting MaxSizeInMegabytes

#### Az.Sql
* Add Instance Failover Group cmdlets from preview release to public release
* Support Azure SQL Server\Database Auditing with new cmdlets.
    - Set-AzSqlServerAudit
    - Get-AzSqlServerAudit
    - Remove-AzSqlServerAudit
    - Set-AzSqlDatabaseAudit
    - Get-AzSqlDatabaseAudit
    - Remove-AzSqlDatabaseAudit
* Remove email constraints from Vulnerability Assessment settings

#### Az.Storage
* Change 2 parameters '-IndexDocument' and '-ErrorDocument404Path' from required to optional  in cmdlet:
    -  Enable-AzStorageStaticWebsite
* Update help of Get-AzStorageBlobContent by add an example
* Show more error information when cmdlet failed with StorageException
* Support create or update Storage account with Azure Files AAD DS Authentication
    -  New-AzStorageAccount
    -  Set-AzStorageAccount
* Support list or close file handles of a file share, file directory or a file
    - Get-AzStorageFileHandle
    - Close-AzStorageFileHandle

#### Az.StorageSync
* This module is now included as a part of the roll-up `Az` module

## 2.3.2 - June 2019
#### Az.Accounts
* Fix bug with incorrect URL being used in some cases for Functions calls
    - More information here: https://github.com/Azure/azure-powershell/issues/8983
* Fix Issue with aliases from AzureRM to Az cmdlets
  - Set-AzureRmVMBootDiagnostics -> Set-AzVMBootDiagnostic
  - Export-AzureRMLogAnalyticThrottledRequests -> Export-AzLogAnalyticThrottledRequest

#### Az.Compute
* New-AzVm and New-AzVmss simple parameter sets now accept the 'ProximityPlacementGroup' parameter.
* Fix typo in 'New-AzVM' reference documentation

#### Az.Dns
* Fixed a typo in 'Set-AzDnsZone' help examples.

#### Az.EventGrid
* Updated to use the 2019-06-01 API version.
* New cmdlets:
    - New-AzureRmEventGridDomain
        - Creates a new Azure Event Grid Domain.
    - Get-AzureRmEventGridDomain
        - Gets the details of an Event Grid Domain, or gets a list of all Event Grid Domains in the current Azure subscription.
    - Remove-AzureRmEventGridDomain
        - Removes an Azure Event Grid Domain.
    - New-AzureRmEventGridDomainKey
        - Regenerates the shared access key for an Azure Event Grid Domain.
    - Get-AzureRmEventGridDomainKey
        - Gets the shared access keys used to publish events to an Event Grid Domain.
    - New-AzureRmEventGridDomainTopic:
        - Creates a new Azure Event Grid Domain Topic.
    - Get-AzureRmEventGridDomainTopic
        - Gets the details of an Event Grid Domain Topic, or gets a list of all Event Grid Domain Topics under specific Event Grid Domain in the current Azure 
    - Remove-AzureRmEventGridDomainTopic:
        - Removes an existing Azure Event Grid Domain Topic.
* Updated cmdlets:
    - New-AzureRmEventGridSubscription/Update-AzureRmEventGridSubscription:
        - Add new mandatory parameters to support piping for the new Event Grid Domain and Event Grid Domain Topic to allow creating new event subscription under these resources.
        - Add new mandatory parameters for specifying the new Event Grid Domain name and/or Event Grid Domain Topic name to allow creating new event subscription under these resources.
        - Add new Parameter sets for domains and domain topics to allow reusing existing parameters (e.g., EndPointType, SubjectBeginsWith, etc).
        - Add new optional parameters for specifying:
            - Event subscription expiration date,
            - Advanced filtering parameters.
        - Add new enum for servicebusqueue as destination.
        - Disallow usage of 'All' in -IncludedEventType option and replace it with 
    - Get-AzEventGridTopic, Get-AzEventGridDomain, Get-AzEventGridDomainTopic, Get-AzEventGridSubscription:
        - Add new optional parameters (Top, ODataQuery and NextLink) to support results pagination and filtering.
    - Remove-AzureRmEventGridSubscription
        - Add new mandatory parameters to support piping for Event Grid Domain and Event Grid Domain Topic to allow removing existing event subscription under these resources.
        - Add new mandatory parameters for specifying the Event Grid Domain name and/or Event Grid Domain Topic name to allow removing existing event subscription under these resources.

#### Az.FrontDoor
* New-AzFrontDoorWafMatchConditionObject
    - Add transforms support and new operator auto-complete value (RegEx)
* New-AzFrontDoorWafManagedRuleObject
    - Add new auto-complete values

#### Az.Network
* Add support for Virtual Network Gateway Resource
    - New cmdlets
        - Get-AzVirtualNetworkGatewayVpnClientConnectionHealth
* Add AvailablePrivateEndpointType
    - New cmdlets 
        - Get-AzAvailablePrivateEndpointType
* Add PrivatePrivateLinkService
    - New cmdlets 
        - Get-AzPrivateLinkService 
        - New-AzPrivateLinkService
        - Remove-AzPrivateLinkService
        - New-AzPrivateLinkServiceIpConfig
        - Set-AzPrivateEndpointConnection
* Add PrivateEndpoint
    - New cmdlets
        - Get-AzPrivateEndpoint
        - New-AzPrivateEndpoint
        - Remove-AzPrivateEndpoint
        - New-AzPrivateLinkServiceConnection
* Updated below commands for feature: UseLocalAzureIpAddress flag on VpnConnection
    - Updated New-AzVpnConnection: Added optional parameter -UseLocalAzureIpAddress to indicate that local azure ip address should be used as source address while initiating connection.
    - Updated Set-AzVpnConnection: Added optional parameter -UseLocalAzureIpAddress to indicate that local azure ip address should be used as source address while initiating connection.
* Added readonly field PeeredConnections in ExpressRoute peering.
* Added readonly field GlobalReachEnabled in ExpressRoute.
* Added breaking change attribute to call out deprecation of AllowGlobalReach field in ExpressRouteCircuit model
* Fixed Issue 8756 Error using TargetListenerID with AzApplicationGatewayRedirectConfiguration cmdlets
* Fixed bug in New-AzApplicationGatewayPathRuleConfig that prevented the rewrite ruleset from being set.
* Fixed displaying of VirtualNetworkTaps in NetworkInterfaceIpConfiguration
* Fixed Cortex Get cmdlets for list all part
* Fixed VirtualHub reference creation for ExpressRouteGateways, VpnGateway
* Added support for Availability Zones in AzureFirewall and NatGateway
* Added cmdlet Get-AzNetworkServiceTag
* Add support for multiple public IP addresses for Azure Firewall
    - Updated New-AzFirewall cmdlet:
        - Added parameter -PublicIpAddress which accepts one or more Public IP Address objects
        - Added parameter -VirtualNetwork which accepts a Virtual Network object
        - Added methods AddPublicIpAddress and RemovePublicIpAddress on firewall object - these accept a Public IP Address object as input
        - Deprecated parameters -PublicIpName and -VirtualNetworkName 
* Updated below commands for feature: Set VpnClient AAD authentication options to Virtual network gateway resource. 
    - Updated New-AzVirtualNetworkGateway: Added optional parameters AadTenantUri,AadAudienceId,AadIssuerUri to set VpnClient AAD authentication options on Gateway.
    - Updated Set-AzVirtualNetworkGateway: Added optional parameter AadTenantUri,AadAudienceId,AadIssuerUri to set VpnClient AAD authentication options on Gateway.
    - Updated Set-AzVirtualNetworkGateway: Added optional switch parameter RemoveAadAuthentication to remove VpnClient AAD authentication options from Gateway.

#### Az.OperationalInsights
* Enable **pergb2018** pricing tier in 'New-AzureRmOperationalInsightsWorkspace' command

#### Az.Resources
* Support for additional Template Export options
    - Add '-SkipResourceNameParameterization' parameter to Export-AzResourceGroup
    - Add '-SkipAllParameterization' parameter to Export-AzResourceGroup
    - Add '-Resource' parameter to Export-AzResourceGroup for exported resource filtering

#### Az.ServiceFabric
* Fix add certificate ByExistingKeyVault getting the wrong thumbprint in some cases

#### Az.Sql
* Fix Advanced Threat Protection storage endpoint suffix
* Fix Advanced Data Security enable overrides Advanced Threat Protection policy
* New Cmdlets for Management.Sql to allow customers to add TDE keys and set TDE protector for managed instances
   - Add-AzSqlInstanceKeyVaultKey
   - Get-AzSqlInstanceKeyVaultKey
   - Remove-AzSqlInstanceKeyVaultKey
   - Get-AzSqlInstanceTransparentDataEncryptionProtector
   - Set-AzSqlInstanceTransparentDataEncryptionProtector

#### Az.Storage
* Support Kind FileStorage and SkuName Premium_ZRS when create Storage account
    - New-AzStorageAccount
* Clarified description of blob immutability cmdlet
    -  Remove-AzRmStorageContainerImmutabilityPolicy

#### Az.Websites
* Optimizes Get-AzWebAppCertificate to filter by resource group on the server instead of the client
* Adds -UseDisasterRecovery switch parameter to Get-AzWebAppSnapshot

## 2.2.0 - June 2019
#### Az.Cdn
* Updated cmdlets to support rulesEngine feature based on API version 2019-04-15.

#### Az.Compute
* Added `NoWait` parameter that starts the operation and returns immediately, before the operation is completed.
    - Updated cmdlets:
        Export-AzLogAnalyticRequestRateByInterval
        Export-AzLogAnalyticThrottledRequest
        Remove-AzVM
        Remove-AzVMAccessExtension
        Remove-AzVMAEMExtension
        Remove-AzVMChefExtension
        Remove-AzVMCustomScriptExtension
        Remove-AzVMDiagnosticsExtension
        Remove-AzVMDiskEncryptionExtension
        Remove-AzVMDscExtension
        Remove-AzVMSqlServerExtension
        Restart-AzVM
        Set-AzVM
        Set-AzVMAccessExtension
        Set-AzVMADDomainExtension
        Set-AzVMAEMExtension
        Set-AzVMBginfoExtension
        Set-AzVMChefExtension
        Set-AzVMCustomScriptExtension
        Set-AzVMDiagnosticsExtension
        Set-AzVMDscExtension
        Set-AzVMExtension
        Start-AzVM
        Stop-AzVM
        Update-AzVM

#### Az.EventHub
* Fix for #9231 - Get-AzEventHubNamespace does not return tags
* Fix for #9230 - Get-AzEventHubNamespace returns ResourceGroup instead of ResourceGroupName

#### Az.Network
* Update ResourceId and InputObject for Nat Gateway
    - Add alias for ResourceId and InputObject

#### Az.PolicyInsights
* Fix Null reference issue in Get-AzPolicyEvent

#### Az.RecoveryServices
* IaaSVM policy minimum retention in days changed to 7 from 1

#### Az.ServiceBus
* Fix for issue #9182 - Get-AzServiceBusNamespace returns ResourceGroup instead of ResourceGroupName

#### Az.ServiceFabric
* Fix typo in error message for 'Update-AzServiceFabricReliability'
* Fix missing character in Service Fabric cmdlines

#### Az.Sql
* Add DnsZonePartner Parameter for New-AzureSqlInstance cmdlet to support AutoDr for Managed Instance.
* Deprecating Get-AzSqlDatabaseSecureConnectionPolicy cmdlet
* Rename Threat Detection cmdlets to Advanced Threat Protection
* New-AzSqlInstance -StorageSizeInGB and -LicenseType parameters are now optional.

#### Az.Websites
* fixes the issue where using  Set-AzWebApp and Set-AzWebAppSlot with -WebApp property was removing the tags

## 2.1.0 - May 2019
#### Az.ApiManagement
* Created new Cmdlets for managing diagnostics at the global and API Scope
    - **Get-AzApiManagementDiagnostic** - Get the diagnostics configured a global or api Scope
    - **New-AzApiManagementDiagnostic** - Create new diagnostics at the global scope or api Scope
    - **New-AzApiManagementHttpMessageDiagnostic** - Create diagnostic setting for which Headers to log and the size of Body Bytes
    - **New-AzApiManagementPipelineDiagnosticSetting** - Create Diagnostic settings for incoming/outgoing HTTP messages to the Gateway.
    - **New-AzApiManagementSamplingSetting** - Create Sampling Setting  for the requests/response for a diagnostic
    - **Remove-AzApiManagementDiagnostic** - Remove a diagnostic entity at global or api scope
    - **Set-AzApiManagementDiagnostic** - Update a diagnostic Entity at global or api scope
* Created new Cmdlets for managing Cache in ApiManagement service
    - **Get-AzApiManagementCache** - Get the details of the Cache specified by identifier or all caches
    - **New-AzApiManagementCache** - Create a new 'default' Cache or Cache in a particular azure 'region'
    - **Remove-AzApiManagementCache** - Remove a cache
    - **Update-AzApiManagementCache** - Update a cache
* Created new Cmdlets for managing API Schema
    - **New-AzApiManagementSchema** - Create a new Schema for an API
    - **Get-AzApiManagementSchema** - Get the schemas configured in the API
    - **Remove-AzApiManagementSchema** - Remove the schema configured in the API
    - **Set-AzApiManagementSchema** - Update the schema configured in the API
* Created new Cmdlet for generating a User Token. 
    - **New-AzApiManagementUserToken** - Generate a new User Token valid for 8 hours by default.Token for the 'GIT' user can be generated using this cmdlet./
* Created a new cmdlet to retrieving the Network Status
    - **Get-AzApiManagementNetworkStatus** - Get the Network status connectivity of resources on which API Management service depends on. This is useful when deploying ApiManagement service into a Virtual Network and validing whether any of the dependencies are broken.
* Updated cmdlet **New-AzApiManagement** to manage ApiManagement service 
    - Added support for the new 'Consumption' SKU
    - Added support to turn the 'EnableClientCertificate' flag on for 'Consumption' SKU
    - The new cmdlet **New-AzApiManagementSslSetting** allows configuring 'TLS/SSL' setting on the 'Backend' and 'Frontend'. This can also be used to configure 'Ciphers' like '3DES' and 'ServerProtocols' like 'Http2' on the 'Frontend' of an ApiManagement service.
    - Added support for configuring the 'DeveloperPortal' hostname on ApiManagement service.
* Updated cmdlets **Get-AzApiManagementSsoToken** to take 'PsApiManagement' object as input
* Updated the cmdlet to display Error Messages inline 
     > PS D:\github\azure-powershell> Set-AzApiManagementPolicy -Context  -PolicyFilePath C:\wrongpolicy.xml -ApiId httpbin
     >   Set-AzApiManagementPolicy : 
     Error Code: ValidationError
     Error Message: One or more fields contain incorrect values:
     Error Details:
        [Code=ValidationError, Message=Error in element 'log-to-eventhub' on line 3, column 10: Logger not found, Target=log-to-eventhub]
* Updated cmdlet **Export-AzApiManagementApi** to export APIs in 'OpenApi 3.0' format
* Updated cmdlet **Import-AzApiManagementApi**
    - To import Api from 'OpenApi 3.0' document specification
    - To override the 'PsApiManagementSchema' property specified in any ('Swagger', 'Wadl', 'Wsdl', 'OpenApi') document.
    - To override the 'ServiceUrl' property specified in any document.
* Updated cmdlet **Get-AzApiManagementPolicy** to return policy in Non-Xml escaped 'format' using 'rawxml'
* Updated cmdlet **Set-AzApiManagementPolicy** to accept policy in Non-Xml escaped 'format' using 'rawxml' and Xml escaped using 'xml'
* Updated cmdlet **New-AzApiManagementApi** 
    - To configure API with 'OpenId' authorization server.
    - To create an API in an 'ApiVersionSet'
    - To clone an API using 'SourceApiId' and 'SourceApiRevision'.
    - Ability to configure 'SubscriptionRequired' at the Api scope. 
* Updated cmdlet **Set-AzApiManagementApi**
    - To configure API with 'OpenId' authorization server.
    - To updated an API into an 'ApiVersionSet'    
    - Ability to configure 'SubscriptionRequired' at the Api scope. 
* Updated cmdlet **New-AzApiManagementRevision**
    - To clone (copy tags, products, operations and policies) an existing revision using 'SourceApiRevision'. The new Revision assumes the 'ApiId' of the parent.
    - To provide an 'ApiRevisionDescription'
    - To override the 'ServiceUrl' when cloning an API.
* Updated cmdlet **New-AzApiManagementIdentityProvider**
    - To configure 'AAD' or 'AADB2C' with an 'Authority'
    - To setup 'SignupPolicy', 'SigninPolicy', 'ProfileEditingPolicy' and 'PasswordResetPolicy'
* Updated cmdlet **New-AzApiManagementSubscription**
    - To account for the new SubscriptonModel using 'Scope' and 'UserId'
    - To account for the old subscription model using 'ProductId' and 'UserId'
    - Add support to enable 'AllowTracing' at the subscription level.
* Updated cmdlet **Set-AzApiManagementSubscription**
    - To account for the new SubscriptonModel using 'Scope' and 'UserId'
    - To account for the old subscription model using 'ProductId' and 'UserId'
    - Add support to enable 'AllowTracing' at the subscription level.
* Updated following cmdlets to accept 'ResourceId' as input
    - 'New-AzApiManagementContext'
        > New-AzApiManagementContext -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso
    - 'Get-AzApiManagementApiRelease'
        > Get-AzApiManagementApiRelease -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso/apis/echo-api/releases/releaseId
    - 'Get-AzApiManagementApiVersionSet'
        > Get-AzApiManagementApiVersionSet -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/constoso/apiversionsets/pathversionset
    - 'Get-AzApiManagementAuthorizationServer'
    - 'Get-AzApiManagementBackend'
        > Get-AzApiManagementBackend -ResourceId /subscriptions/subid/resourceGroups/rgName/providers/Microsoft.ApiManagement/service/contoso/backends/servicefabric
    - 'Get-AzApiManagementCertificate' 
    - 'Remove-AzApiManagementApiVersionSet'
    - 'Remove-AzApiManagementSubscription'

#### Az.Automation
* Updated Get-AzAutomationJobOutputRecord to handle JSON and Text record values.
    - Fix for issue https://github.com/Azure/azure-powershell/issues/7977
    - Fix for issue https://github.com/Azure/azure-powershell/issues/8600
* Changed behavior for Start-AzAutomationDscCompilationJob to just start the job instead of waiting for its completion.
    * Fix for issue https://github.com/Azure/azure-powershell/issues/8347
* Fix for Get-AzAutomationDscNode when using -Name returns all node. Now it returns matching node only.

#### Az.Compute
* Add ProtectFromScaleIn and ProtectFromScaleSetAction parameters to Update-AzVmssVM cmdlet.
* New-AzVM wimple parameter set now uses by default an available location if 'East US' is not supported

#### Az.DataLakeStore
* Update the ADLS sdk to use httpclient, integrate dataplane testing with azure framework

#### Az.Monitor
* Fixed incorrect parameter names in help examples

#### Az.Network
* Add DisableBgpRoutePropagation flag to Effective Route Table output
    - Updated cmdlet:
        - Get-AzEffectiveRouteTable
* Fix double dash in New-AzApplicationGatewayTrustedRootCertificate documentation

#### Az.Resources
* Add new cmdlet Get-AzureRmDenyAssignment for retrieving deny assignments

#### Az.Sql
* Rename Advanced Threat Protection cmdlets to Advanced Data Security and enable Vulnerability Assessment by default

## 2.0.0 - May 2019
#### Az.Accounts
* Update Authentication Library to fix ADFS issues with username/password auth

#### Az.CognitiveServices
* Only display Bing disclaimer for Bing Search Services.
* Improve error when create account failed.

#### Az.Compute
* Proximity placement group feature.
    - The following new cmdlets are added:
	    New-AzProximityPlacementGroup
		Get-AzProximityPlacementGroup
		Remove-AzProximityPlacementGroup
	- The new parameter, ProximityPlacementGroupId, is added to the following cmdlets:
	    New-AzAvailabilitySet
		New-AzVMConfig
		New-AzVmssConfig
* StorageAccountType parameter is added to New-AzGalleryImageVersion.
* TargetRegion of New-AzGalleryImageVersion can contain StorageAccountType.
* SkipShutdown switch parameter is added to Stop-AzVM and Stop-AzVmss		
* Breaking changes
    - Set-AzVMBootDiagnostics is changed to Set-AzVMBootDiagnostic.
    - Export-AzLogAnalyticThrottledRequests is changed to Export-AzLogAnalyticThrottledRequests.

#### Az.DeploymentManager
* First Generally Available release of Azure Deployment Manager cmdlets

#### Az.Dns
* Automatic DNS NameServer Delegation
    - Create DNS zone cmdlet accepts parent zone name as additional optional parameter.
    - Adds NS records in the parent zone for newly created child zone.

#### Az.FrontDoor
* First Generally Available Release of Azure FrontDoor cmdlets
* Rename WAF cmdlets to include 'Waf'
    - `Get-AzFrontDoorFireWallPolicy --> Get-AzFrontDoorWafPolicy`
    - `New-AzFrontDoorCustomRuleObject --> New-AzFrontDoorWafCustomRuleObject`
    - `New-AzFrontDoorFireWallPolicy --> New-AzFrontDoorWafPolicy`
    - `New-AzFrontDoorManagedRuleObject --> New-AzFrontDoorWafManagedRuleObject`
    - `New-AzFrontDoorManagedRuleOverrideObject --> New-AzFrontDoorWafManagedRuleOverrideObject`
    - `New-AzFrontDoorMatchConditionObject --> New-AzFrontDoorWafMatchConditionObject`
    - `New-AzFrontDoorRuleGroupOverrideObject --> New-AzFrontDoorWafRuleGroupOverrideObject`
    - `Remove-AzFrontDoorFireWallPolicy --> Remove-AzFrontDoorWafPolicy`
    - `Update-AzFrontDoorFireWallPolicy --> Update-AzFrontDoorWafPolicy`
#### Az.HDInsight
* Removed two cmdlets:
    - Grant-AzHDInsightHttpServicesAccess
    - Revoke-AzHDInsightHttpServicesAccess
* Added a new cmdlet Set-AzHDInsightGatewayCredential to replace Grant-AzHDInsightHttpServicesAccess
* Update cmdlet Get-AzHDInsightJobOutput to distinguish reader role and hdinsight operator role:
    - Users with reader role need to specify 'DefaultStorageAccountKey' parameter explicitly, otherwise error occurs.
	- Users with hdinsight operator role will not be affected.

#### Az.Monitor
* New cmdlets for SQR API (Scheduled Query Rule)  
    - New-AzScheduledQueryRuleAlertingAction
	- New-AzScheduledQueryRuleAznsActionGroup
	- New-AzScheduledQueryRuleLogMetricTrigger
	- New-AzScheduledQueryRuleSchedule
	- New-AzScheduledQueryRuleSource
	- New-AzScheduledQueryRuleTriggerCondition
	- New-AzScheduledQueryRule
	- Get-AzScheduledQueryRule
	- Set-AzScheduledQueryRule
	- Update-AzScheduledQueryRule
	- Remove-AzScheduledQueryRule
	- [More](https://docs.microsoft.com/en-us/rest/api/monitor/scheduledqueryrules) information about SQR API
	- Updated Az.Monitor.md to include cmdlets for GenV2(non classic) metric-based alert rule

#### Az.Network
* Add support for Nat Gateway Resource
    - New cmdlets
        - New-AzNatGateway
        - Get-AzNatGateway
        - Set-AzNatGateway
        - Remove-AzNatGateway
   - Updated cmdlets
        - New-AzureVirtualNetworkSubnetConfigCommand
        - Add-AzureVirtualNetworkSubnetConfigCommand
* Updated below commands for feature: Custom routes set/remove on Brooklyn Gateway.
    - Updated New-AzVirtualNetworkGateway: Added optional parameter -CustomRoute to set the address prefixes as custom routes to set on Gateway.
    - Updated Set-AzVirtualNetworkGateway: Added optional parameter -CustomRoute to set the address prefixes as custom routes to set on Gateway.

#### Az.PolicyInsights
* Support for querying policy evaluation details.
    - Add '-Expand' parameter to Get-AzPolicyState. Support '-Expand PolicyEvaluationDetails'.

#### Az.RecoveryServices
* Support for Cross subscription Azure to Azure site recovery.
* Marking upcoming breaking changes for Azure Site Recovery.
* Fix for Azure Site Recovery recovery plan end action plan.
* Fix for Azure Site Recovery Update network mapping for Azure to Azure.
* Fix for Azure Site Recovery update protection direction for Azure to Azure for managed disk.
* Other minor fixes.

#### Az.Relay
* Fix typos in customer-facing messages

#### Az.ServiceBus
* Added new cmdlets for NetworkRuleSet of Namespace

#### Az.Storage
* Upgrade to Storage Client Library 10.0.1 (the namespace of all objects from this SDK change from 'Microsoft.WindowsAzure.Storage.*' to 'Microsoft.Azure.Storage.*')
* Upgrade to Microsoft.Azure.Management.Storage 11.0.0, to support new API version 2019-04-01.
* The default Storage account Kind in Create Storage account change from 'Storage' to 'StorageV2'
    - New-AzStorageAccount
* Change the Storage account cmdlet output Sku.Name to be aligned with input SkuName by add '-', like 'StandardLRS' change to 'Standard_LRS'
    - New-AzStorageAccount
    - Get-AzStorageAccount
    - Set-AzStorageAccount

#### Az.Websites
* 'Kind' property will now be set for PSSite objects returned by Get-AzWebApp
* Get-AzWebApp*Metrics and Get-AzAppServicePlanMetrics marked deprecated

## 1.8.0 - April 2019
### Highlights since the last major release
* General availability of `Az` module
* For more information about the `Az` module, please visit the following: https://aka.ms/azps-announce
* Added Location, ResourceGroup, and ResourceName completers: https://azure.microsoft.com/en-us/blog/completers-in-azure-powershell/
* Added wildcard support to Get cmdlets for Az.Compute and Az.Network
* Added interactive and username/password authentication for Windows PowerShell 5.1 only
* Added support for Python 2 runbooks in Az.Automation
* Az.LogicApp: New cmdlets for Integration Account Assemblies and Batch Configuration

#### Az.Accounts
* Update Uninstall-AzureRm to correctly delete modules in Mac

#### Az.Batch
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.Cdn
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.CognitiveServices
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.Compute
* Fix issue with AEM installation if resource ids of disks had lowercase resourcegroups in resource id
* Updated cmdlets with plural nouns to singular, and deprecated plural names.
* Fix documentation for wildcards

#### Az.DataFactory
* Add SsisProperties if NodeCount not null for managed integration runtime.

#### Az.DataLakeStore
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.EventGrid
* Updated the help text for endpoint to indicate that resources should be created before using the create/update event subscription cmdlets.

#### Az.EventHub
* Added new cmdlets for NetworkRuleSet of Namespace 

#### Az.HDInsight
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.IotHub
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.KeyVault
* Updated cmdlets with plural nouns to singular, and deprecated plural names.
* Fix documentation for wildcards

#### Az.MachineLearning
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.Media
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.Monitor
  * New cmdlets for GenV2(non classic) metric-based alert rule
      - New-AzMetricAlertRuleV2DimensionSelection
      - New-AzMetricAlertRuleV2Criteria
      - Remove-AzMetricAlertRuleV2
      - Get-AzMetricAlertRuleV2
      - Add-AzMetricAlertRuleV2
  * Updated Monitor SDK to version 0.22.0-preview

#### Az.Network
* Updated cmdlets with plural nouns to singular, and deprecated plural names.
* Fix documentation for wildcards

#### Az.NotificationHubs
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.OperationalInsights
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.PowerBIEmbedded
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.RecoveryServices
* Updated cmdlets with plural nouns to singular, and deprecated plural names.
* Updated table format for SQL in azure VM
* Added alternate method to fetch location in AzureFileShare
* Updated ScheduleRunDays in SchedulePolicy object according to timezone

#### Az.RedisCache
* Updated cmdlets with plural nouns to singular, and deprecated plural names.

#### Az.Resources
* Fix documentation for wildcards

#### Az.Sql
* Replace dependency on Monitor SDK with common code
* Updated cmdlets with plural nouns to singular, and deprecated plural names.
* Enhanced process of multiple columns classification.
* Include sku properties (sku name, family, capacity) in response from Get-AzSqlServerServiceObjective and format as table by default.
* Ability to Get-AzSqlServerServiceObjective by location without needing a preexisting server in the region.
* Support for time zone parameter in Managed Instance create.
* Fix documentation for wildcards

#### Az.Websites
* fixes the Set-AzWebApp and Set-AzWebAppSlot to not remove the tags on execution
* Updated cmdlets with plural nouns to singular, and deprecated plural names.
* Updated the WebSites SDK.
* Removed the AdminSiteName property from PSAppServicePlan.

## 1.7.0 - April 2019
### Highlights since the last major release
* General availability of `Az` module
* For more information about the `Az` module, please visit the following: https://aka.ms/azps-announce
* Added Location, ResourceGroup, and ResourceName completers: https://azure.microsoft.com/en-us/blog/completers-in-azure-powershell/
* Added wildcard support to Get cmdlets for Az.Compute and Az.Network
* Added interactive and username/password authentication for Windows PowerShell 5.1 only
* Added support for Python 2 runbooks in Az.Automation
* Az.LogicApp: New cmdlets for Integration Account Assemblies and Batch Configuration

#### Az.Accounts
* Updated Add-AzEnvironment and Set-AzEnvironment to accept parameter AzureAnalysisServicesEndpointResourceId

#### Az.AnalysisServices
* Using ServiceClient in dataplane cmdlets and removing the original authentication logic
* Making Add-AzureASAccount a wrapper of Connect-AzAccount to avoid a breaking change

#### Az.Automation
* Fixed New-AzAutomationSoftwareUpdateConfiguration cmdlet bug for Inclusions. Now parameter IncludedKbNumber and IncludedPackageNameMask should work.
* Bug fix for azure automation update management dynamic group

#### Az.Compute
* Add HyperVGeneration parameter to New-AzDiskConfig and New-AzSnapshotConfig
* Allow VM creation with galley image from other tenants. 

#### Az.ContainerInstance
* Fixed issue in the -Command parameter of New-AzContainerGroup which added a trailing empty argument

#### Az.DataFactory
* Updated ADF .Net SDK version to 3.0.2
* Updated Set-AzDataFactoryV2 cmdlet with extra parameters for RepoConfiguration related settings.

#### Az.Resources
* Improve handling of providers for 'Get-AzResource' when providing '-ResourceId' or '-ResourceGroupName', '-Name' and '-ResourceType' parameters
* Improve error handling for 'Test-AzDeployment' and 'Test-AzResourceGroupDeployment'
    - Handle errors thrown outside of deployment validation and include them in output of command instead
    - More information here: https://github.com/Azure/azure-powershell/issues/6856
* Add '-IgnoreDynamicParameters' switch parameter to set of deployment cmdlets to skip prompt in script and job scenarios
    - More information here: https://github.com/Azure/azure-powershell/issues/6856

#### Az.Sql
* Support Database Data Classification.

#### Az.Storage
* Report detail error when create Storage context with parameter -UseConnectedAccount, but without login Azure account
    - New-AzStorageContext
* Support Manage Blob Service Properties of a specified Storage account with Management plane API
    - Update-AzStorageBlobServiceProperty
    - Get-AzStorageBlobServiceProperty
    - Enable-AzStorageBlobDeleteRetentionPolicy
    - Disable-AzStorageBlobDeleteRetentionPolicy
* -AsJob support for Blob and file upload and download cmdlets
    - Get-AzStorageBlobContent
    - Set-AzStorageBlobContent
    - Get-AzStorageFileContent
    - Set-AzStorageFileContent

## 1.6.0 - March 2019
### Highlights since the last major release
* General availability of `Az` module
* For more information about the `Az` module, please visit the following: https://aka.ms/azps-announce
* Added Location, ResourceGroup, and ResourceName completers: https://azure.microsoft.com/en-us/blog/completers-in-azure-powershell/
* Added wildcard support to Get cmdlets for Az.Compute and Az.Network
* Added interactive and username/password authentication for Windows PowerShell 5.1 only
* Added support for Python 2 runbooks in Az.Automation
* Az.LogicApp: New cmdlets for Integration Account Assemblies and Batch Configuration

#### Az.Automation
* Azure automation update management change to support the following new features :
    * Dynamic grouping
    * Pre-Post script
    * Reboot Setting

#### Az.Compute
* Fix issue with path resolution in Get-AzVmBootDiagnosticsData
* Update Compute client library to 25.0.0.

#### Az.KeyVault
* Added wildcard support to KeyVault cmdlets

#### Az.Network
* Add Threat Intelligence support for Azure Firewall
* Add Application Gateway Firewall Policy top level resource and Custom Rules

#### Az.RecoveryServices
* Added SnapshotRetentionInDays in Azure VM policy to support Instant RP
* Added pipe support for unregister container

#### Az.Resources
* Update wildcard support for Get-AzResource and Get-AzResourceGroup
* Update credentials used when making generic calls to ARM

#### Az.Sql
* changed Threat Detection's cmdlets param (ExcludeDetectionType) from DetectionType to string[] to make it future proof when new DetectionTypes are added and to support autocomplete as well.

#### Az.Storage
* Support Get/Set/Remove Management Policy on a Storage account
    - Set-AzStorageAccountManagementPolicy
    - Get-AzStorageAccountManagementPolicy
    - Remove-AzStorageAccountManagementPolicy
    - Add-AzStorageAccountManagementPolicyAction
    - New-AzStorageAccountManagementPolicyFilter
    - New-AzStorageAccountManagementPolicyRule

#### Az.Websites
* Fix ARM template bug that breaks cloning all slots using 'New-AzWebApp -IncludeSourceWebAppSlots' 

## 1.5.0 - March 2019
#### Az.Accounts
* Add 'Register-AzModule' command to support AutoRest generated cmdlets
* Update examples for Connect-AzAccount

#### Az.Automation
* Fixed issue when retreiving certain monthly schedules in several Azure Automation cmdlets
* Fix Get-AzAutomationDscNode returning just top 20 nodes. Now it returns all nodes

#### Az.Cdn
* Added new Powershell cmdlets for Enable/Disable Custom Domain Https and deprecated the old ones

#### Az.Compute
* Add wildcard support to Get cmdlets

#### Az.DataFactory
* Updated ADF .Net SDK version to 3.0.1

#### Az.LogicApp
* Fix for ListWorkflows only retrieving the first page of results

#### Az.Network
* Add wildcard support to Network cmdlets

#### Az.RecoveryServices
* Added Sql server in Azure VM support
* SDK Update
* Removed VMappContainer check in Get-ProtectableItem
* Added Name and ServerName as parameters for Get-ProtectableItem

#### Az.Resources
* Add `-TemplateObject` parameter to deployment cmdlets
    - More information here: https://github.com/Azure/azure-powershell/issues/2933
* Fix issue when piping the result of `Get-AzResource` to `Set-AzResource`
    - More information here: https://github.com/Azure/azure-powershell/issues/8240
* Fix issue with JSON data type change when running `Set-AzResource`
    - More information here: https://github.com/Azure/azure-powershell/issues/7930

#### Az.Sql
* Updating AuditingEndpointsCommunicator.
    - Fixing the behavior of an edge case while creating new diagnostic settings.

#### Az.Storage
* Support Kind BlockBlobStorage when create Storage account
       - New-AzStorageAccount

## 1.4.0 - February 2019
#### Az.AnalysisServices
* Deprecated AddAzureASAccount cmdlet

#### Az.Automation
* Update help for Import-AzAutomationDscNodeConfiguration
* Added configuration name validation to Import-AzAutomationDscConfiguration cmdlet
* Improved error handling for Import-AzAutomationDscConfiguration cmdlet

#### Az.CognitiveServices
* Added CustomSubdomainName as a new optional parameter for New-AzCognitiveServicesAccount which is used to specify subdomain for the resource.

#### Az.Compute
* Fix issue with ID parameter sets
* Update Get-AzVMExtension to list all installed extension if Name parameter is not provided
* Add Tag and ResourceId parameters to Update-AzImage cmdlet
* Get-AzVmssVM without instance ID and with InstanceView can list VMSS VMs with instance view.

#### Az.DataLakeStore
* Add cmdlets for ADL deleted item enumerate and restore

#### Az.EventHub
* Added new boolean property SkipEmptyArchives to Skip Empty Archives in CaptureDescription class of Eventhub 

#### Az.KeyVault
* Fix tagging on Set-AzKeyVaultSecret

#### Az.LogicApp
* Add in Basic sku for Integration Accounts
* Add in XSLT 2.0, XSLT 3.0 and Liquid Map Types
* New cmdlets for Integration Account Assemblies
	- Get-AzIntegrationAccountAssembly
	- New-AzIntegrationAccountAssembly
	- Remove-AzIntegrationAccountAssembly
	- Set-AzIntegrationAccountAssembly
* New cmdlets for Integration Account Batch Configuration
	- Get-AzIntegrationAccountBatchConfiguration
	- New-AzIntegrationAccountBatchConfiguration
	- Remove-AzIntegrationAccountBatchConfiguration
	- Set-AzIntegrationAccountBatchConfiguration
* Update Logic App SDK to version 4.1.0

#### Az.Monitor
* Update help for Get-AzMetric

#### Az.Network
* Update help example for Add-AzApplicationGatewayCustomError

#### Az.OperationalInsights
* Additional support for New and Get ApplicationInsights data source.
    - Added new 'ApplicationInsights' kind to support Get specific and Get all ApplicationInsights data sources for given workspace. 
    - Added New-AzOperationalInsightsApplicationInsightsDataSource cmdlet for creating data source by given Application-Insights resource parameters: subscription Id, resourceGroupName and name. 

#### Az.Resources
* Fix for issue https://github.com/Azure/azure-powershell/issues/8166
* Fix for issue https://github.com/Azure/azure-powershell/issues/8235
* Fix for issue https://github.com/Azure/azure-powershell/issues/6219
* Fix bug preventing repeat creation of KeyCredentials

#### Az.Sql
* Add support for SQL DB Hyperscale tier
* Fixed bug where restore could fail due to setting unnecessary properties in restore request

#### Az.Websites
* Correct example in Get-AzWebAppSlotMetrics

## 1.3.0 - February 2019
#### Az.Accounts
* Update to latest version of ClientRuntime

#### Az.AnalysisServices
General availability for Az.AnalysisServices module.

#### Az.Compute
* AEM extension: Add support for UltraSSD and P60,P70 and P80 disks
* Update help description for Set-AzVMBootDiagnostics
* Update help description and example for Update-AzImage

#### Az.RecoveryServices
General availability for Az.RecoveryServices module.

#### Az.Resources
* Fix tagging for resource groups 
    - More information here: https://github.com/Azure/azure-powershell/issues/8166
* Fix issue where `Get-AzureRmRoleAssignment` doesn't respect -ErrorAction 
    - More information here: https://github.com/Azure/azure-powershell/issues/8235

#### Az.Sql
* Add Get/Set AzSqlDatabaseBackupShortTermRetentionPolicy
* Fix issue where not being logged into Azure account would result in nullref exception when executing SQL cmdlets
* Fixed null ref exception in Get-AzSqlCapability

## 1.2.1 - January 2019
#### Az.Accounts
* Release with correct version of Authentication

#### Az.AnalysisServices
* Release with updated Authentication dependency

#### Az.RecoveryServices
* Release with updated Authentication dependency

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