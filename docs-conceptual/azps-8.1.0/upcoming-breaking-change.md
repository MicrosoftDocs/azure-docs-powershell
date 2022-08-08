---
title: Upcoming breaking changes in Azure PowerShell
description: Learn about upcoming breaking changes to the Azure PowerShell module
ms.date: 08/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
---

# Upcoming breaking changes in Azure PowerShell

## Az.AnalysisServices

### `Add-AzAnalysisServicesAccount`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet is being deprecated. There will be no replacement for it.

## Az.ApiManagement

### `Add-AzApiManagementRegion`

- Parameter breaking-change will happen to all parameter sets
  - `-Sku`
    - The parameter : 'Sku' is changing.
    The type of the parameter is changing from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'String'.

### `New-AzApiManagement`

- Parameter breaking-change will happen to all parameter sets
  - `-Sku`
    - The parameter : 'Sku' is changing.
    The type of the parameter is changing from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'String'.

### `New-AzApiManagementOperation`

- Parameter breaking-change will happen to all parameter sets
  - `-Request`
    - Change Request.Representations.Sample to Request.Representations.Example
  - `-Responses`
    - Change Responses.Representations.Sample to Responses.Representations.Example

### `Set-AzApiManagementOperation`

- Parameter breaking-change will happen to all parameter sets
  - `-Request`
    - Change Request.Representations.Sample Request.Representations.Example
  - `-Responses`
    - Change Responses.Representations.Sample to Responses.Representations.Example

### `Update-AzApiManagementRegion`

- Parameter breaking-change will happen to all parameter sets
  - `-Sku`
    - The parameter : 'Sku' is changing.
    The type of the parameter is changing from 'Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSku' to 'String'.


## Az.Batch

### `New-AzBatchPool`

- Parameter breaking-change will happen to all parameter sets
  - `-TaskSlotsPerNode`
    - The parameter : 'MaxTasksPerComputeNode' is changing.


## Az.Billing

### `Get-AzBillingPeriod`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet is being deprecated. There will be no replacement for it.

## Az.EventHub

### `Get-AzEventHubNamespace`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes' is changing
  - The following properties in the output type are being deprecated : 'ResourceGroup'
  - The following properties are being added to the output type : 'ResourceGroupName' 'Tags'
### `New-AzEventHubCluster`

- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - 'Name' Parameter is being deprecated from ClusterResourceIdParameterSet without being replaced. ResourceId's are implicit of resource name.
  - `-ResourceId`
    - 'ResourceId' Parameter is being deprecated without being replaced.

### `New-AzEventHubNamespace`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes' is changing
  - The following properties in the output type are being deprecated : 'ResourceGroup' 'Identity'
  - The following properties are being added to the output type : 'ResourceGroupName' 'Tags' 'IdentityType'
### `Set-AzEventHubCluster`

- Parameter breaking-change will happen to all parameter sets
  - `-Location`
    - Location Parameter is being deprecated without being replaced
  - `-Name`
    - 'Name' Parameter is being deprecated from ClusterResourceIdParameterSet without being replaced. ResourceId's are implicit of resource name.

### `Set-AzEventHubNamespace`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes' is changing
  - The following properties in the output type are being deprecated : 'ResourceGroup' 'IdentityUserDefined' 'Identity' 'KeyProperty'
  - The following properties are being added to the output type : 'ResourceGroupName' 'Tags' 'IdentityType' 'EncryptionConfig'

## Az.HDInsight

### `New-AzHDInsightCluster`

- Parameter breaking-change will happen to all parameter sets
  - `-RdpAccessExpiry`
    - This parameter is being deprecated.
  - `-RdpCredential`
    - This parameter is being deprecated.


## Az.LogicApp

### `New-AzIntegrationAccountMap`

- Parameter breaking-change will happen to all parameter sets
  - `-ContentType`
    - ContentType is being deprecated without being replaced. It will be inferred from MapType

### `Set-AzIntegrationAccountMap`

- Parameter breaking-change will happen to all parameter sets
  - `-ContentType`
    - ContentType is being deprecated without being replaced. It will be inferred from MapType


## Az.NetAppFiles

### `Get-AzNetAppFilesBackupPolicy`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesBackupPolicy' is changing
  - The following properties in the output type are being deprecated : 'YearlyBackupsToKeep'
### `Get-AzNetAppFilesVault`

- Cmdlet breaking-change will happen to all parameter set

  - The output type is changing from the existing type :'Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesBackupPolicy' to the new type :'PSNetAppFilesVault'
### `New-AzNetAppFilesBackupPolicy`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesBackupPolicy' is changing
  - The following properties in the output type are being deprecated : 'YearlyBackupsToKeep'
- Parameter breaking-change will happen to all parameter sets
  - `-YearlyBackupsToKeep`
    - Parameter YearlyBackupsToKeep is invalid and preserved for compatibility.

### `New-AzNetAppFilesVolume`

- Parameter breaking-change will happen to all parameter sets
  - `-Snapshot`
    - Snapshot invalid and preserved for compatibility. Parameter SnapshotPolicyId should be used instead
  - `-UnixPermission`
    - Parameter Alias UnixPermissions will be removed, please use UnixPermission.

### `Remove-AzNetAppFilesBackupPolicy`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesBackupPolicy' is changing
  - The following properties in the output type are being deprecated : 'YearlyBackupsToKeep'
### `Set-AzNetAppFilesBackupPolicy`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesBackupPolicy' is changing
  - The following properties in the output type are being deprecated : 'YearlyBackupsToKeep'
- Parameter breaking-change will happen to all parameter sets
  - `-YearlyBackupsToKeep`
    - Parameter YearlyBackupsToKeep is invalid and preserved for compatibility.

### `Update-AzNetAppFilesBackupPolicy`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesBackupPolicy' is changing
  - The following properties in the output type are being deprecated : 'YearlyBackupsToKeep'
- Parameter breaking-change will happen to all parameter sets
  - `-YearlyBackupsToKeep`
    - Parameter YearlyBackupsToKeep is invalid and preserved for compatibility.


## Az.Network

### `Add-AzExpressRouteCircuitAuthorization`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Add-AzExpressRouteCircuitConnectionConfig`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Add-AzExpressRouteCircuitPeeringConfig`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Add-AzVirtualHubRoute`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'New-AzVHubRoute' is replacing this cmdlet.
### `Add-AzVirtualHubRouteTable`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'New-AzVHubRouteTable' is replacing this cmdlet.
### `Add-AzVirtualRouterPeer`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Add-AzRouteServerPeer' is replacing this cmdlet.
### `Get-AzExpressRouteCircuit`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Get-AzExpressRouteCircuitAuthorization`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Get-AzExpressRouteCircuitPeeringConfig`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Get-AzPrivateEndpointConnection`

- Parameter breaking-change will happen to all parameter sets
  - `-Description`
    - Parameter is being deprecated without being replaced

### `Get-AzVirtualHubRouteTable`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Get-AzVHubRouteTable' is replacing this cmdlet.
### `Get-AzVirtualRouter`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Get-AzRouteServer' is replacing this cmdlet.
### `Get-AzVirtualRouterPeer`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Get-AzRouteServerPeer' is replacing this cmdlet.
### `Get-AzVirtualRouterPeerAdvertisedRoute`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Get-AzRouteServerPeerAdvertisedRoute' is replacing this cmdlet.
### `Get-AzVirtualRouterPeerLearnedRoute`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Get-AzRouteServerPeerLearnedRoute' is replacing this cmdlet.
### `Move-AzExpressRouteCircuit`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `New-AzApplicationGateway`

- Parameter breaking-change will happen to all parameter sets
  - `-UserAssignedIdentityId`
    - The parameter : 'UserAssignedIdentityId' is being replaced by parameter : 'Identity'.

### `New-AzExpressRouteCircuit`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `New-AzFirewall`

- Parameter breaking-change will happen to all parameter sets
  - `-PublicIpName`
    - This parameter will be removed in an upcoming breaking change release. After this point the Public IP Address will be provided as a list of one or more objects instead of a string.
  - `-VirtualNetworkName`
    - This parameter will be removed in an upcoming breaking change release. After this point the Virtual Network will be provided as an object instead of a string.

### `New-AzFirewallPolicyApplicationRule`

- Parameter breaking-change will happen to all parameter sets
  - `-SourceAddress`
    - This parameter is becoming optional as SourceIpGroup can be provided without this.

### `New-AzFirewallPolicyNetworkRule`

- Parameter breaking-change will happen to all parameter sets
  - `-SourceAddress`
    - This parameter is becoming optional as SourceIpGroup can be provided without this.

### `New-AzPrivateLinkServiceIpConfig`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSPrivateLinkServiceIpConfiguration' is changing
  - The following properties in the output type are being deprecated : 'PublicIPAddress'
  - The following properties are being added to the output type : 'Primary'
- Parameter breaking-change will happen to all parameter sets
  - `-PublicIpAddress`
    - Parameter is being deprecated without being replaced

### `New-AzVirtualHub`

- Parameter breaking-change will happen to all parameter sets
  - `-HubVnetConnection`
    - HubVnetConnection parameter is deprecated. Use *VirtualHubVnetConnection* commands
  - `-PreferredRoutingGateway`
    - PreferredRoutingGateway parameter is deprecated. Use *HubRoutingPreference* property
  - `-RouteTable`
    - Parameter is being deprecated without being replaced. Use *VHubRouteTable* commands.

### `New-AzVirtualHubRoute`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'New-AzVHubRoute' is replacing this cmdlet.
### `New-AzVirtualHubRouteTable`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'New-AzVHubRouteTable' is replacing this cmdlet.
### `New-AzVirtualHubVnetConnection`

- Parameter breaking-change will happen to all parameter sets
  - `-EnableInternetSecurity`
    - The parameter : 'EnableInternetSecurity' is changing.
    The type of the parameter is changing from 'System.Management.Automation.SwitchParameter' to 'EnableInternetSecurityFlag'.

### `New-AzVirtualRouter`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'New-AzRouteServer' is replacing this cmdlet.
### `Remove-AzExpressRouteCircuitAuthorization`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Remove-AzExpressRouteCircuitConnectionConfig`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Remove-AzExpressRouteCircuitPeeringConfig`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Remove-AzPrivateEndpointConnection`

- Parameter breaking-change will happen to all parameter sets
  - `-Description`
    - Parameter is being deprecated without being replaced

### `Remove-AzVirtualHubRouteTable`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Remove-AzVHubRouteTable' is replacing this cmdlet.
### `Remove-AzVirtualRouter`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Remove-AzRouteServer' is replacing this cmdlet.
### `Remove-AzVirtualRouterPeer`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Remove-AzRouteServerPeer' is replacing this cmdlet.
### `Set-AzExpressRouteCircuit`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Set-AzExpressRouteCircuitConnectionConfig`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Set-AzExpressRouteCircuitPeeringConfig`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Network.Models.PSExpressRouteCircuit' is changing
  - The following properties in the output type are being deprecated : 'AllowGlobalReach'
### `Set-AzVirtualHub`

- Parameter breaking-change will happen to all parameter sets
  - `-RouteTable`
    - Parameter is being deprecated without being replaced. Use *VHubRouteTable* commands.

### `Update-AzVirtualHub`

- Parameter breaking-change will happen to all parameter sets
  - `-HubVnetConnection`
    - HubVnetConnection parameter is deprecated. Use *VirtualHubVnetConnection* commands
  - `-PreferredRoutingGateway`
    - PreferredRoutingGateway parameter will be deprecated. Use *HubRoutingPreference* parameter
  - `-RouteTable`
    - Parameter is being deprecated without being replaced. Use *VHubRouteTable* commands.

### `Update-AzVirtualRouter`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Update-AzRouteServer' is replacing this cmdlet.
### `Update-AzVirtualRouterPeer`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet 'Update-AzRouteServerPeer' is replacing this cmdlet.

## Az.OperationalInsights

### `Get-AzOperationalInsightsCluster`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.OperationalInsights.Models.PSCluster' is changing
  - The following properties in the output type are being deprecated : 'NextLink' 'Sku'
### `New-AzOperationalInsightsCluster`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.OperationalInsights.Models.PSCluster' is changing
  - The following properties in the output type are being deprecated : 'NextLink' 'Sku'
### `Update-AzOperationalInsightsCluster`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.OperationalInsights.Models.PSCluster' is changing
  - The following properties in the output type are being deprecated : 'NextLink' 'Sku'

## Az.Resources

### `Export-AzResourceGroup`

- Parameter breaking-change will happen to all parameter sets
  - `-ApiVersion`
    - Parameter is being deprecated without being replaced. Using the lastest possible API version will become the default behavior.

### `Get-AzManagementGroup`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `Get-AzManagementGroupHierarchySetting`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `Get-AzManagementGroupNameAvailability`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `Get-AzManagementGroupSubscription`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `Get-AzPolicyAssignment`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment' is changing
  - The following properties are being added to the output type : 'Identity'
### `New-AzManagementGroup`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `New-AzManagementGroupHierarchySetting`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `New-AzManagementGroupSubscription`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `New-AzPolicyAssignment`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment' is changing
  - The following properties are being added to the output type : 'Identity'
- Parameter breaking-change will happen to all parameter sets
  - `-AssignIdentity`
    - Parameter AssignIdentity is deprecated and will be removed in future releases. Please use the 'IdentityType' parameter instead.

### `Remove-AzManagementGroup`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `Remove-AzManagementGroupHierarchySetting`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `Remove-AzManagementGroupSubscription`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `Set-AzPolicyAssignment`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment' is changing
  - The following properties are being added to the output type : 'Identity'
- Parameter breaking-change will happen to all parameter sets
  - `-AssignIdentity`
    - Parameter AssignIdentity is deprecated and will be removed in future releases. Please use the 'IdentityType' parameter instead.

### `Update-AzManagementGroup`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.

### `Update-AzManagementGroupHierarchySetting`

- Parameter breaking-change will happen to all parameter sets
  - `-GroupName`
    - We will replace GroupName with GroupId to make it more clear.


## Az.Security

### `Get-AzSecurityAlert`

- Cmdlet breaking-change will happen to all parameter set

  - The output type is changing from the existing type :'Microsoft.Azure.Commands.Security.Models.Alerts.PSSecurityAlert' to the new type :'PSSecurityAlertV3'
### `Set-AzSecurityAlert`

- Parameter breaking-change will happen to all parameter sets
  - `-InputObject`
    - The parameter : 'InputObject' is changing.
    The type of the parameter is changing from 'Microsoft.Azure.Commands.Security.Models.Alerts.PSSecurityAlert' to 'PSSecurityAlertV3'.


## Az.ServiceBus

### `Get-AzServiceBusNamespace`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSNamespaceAttributes' is changing
  - The following properties in the output type are being deprecated : 'ResourceGroup'
  - The following properties are being added to the output type : 'ResourceGroupName'
### `New-AzServiceBusNamespace`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSNamespaceAttributes' is changing
  - The following properties in the output type are being deprecated : 'ResourceGroup'
  - The following properties are being added to the output type : 'ResourceGroupName'
### `Set-AzServiceBusNamespace`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.ServiceBus.Models.PSNamespaceAttributes' is changing
  - The following properties in the output type are being deprecated : 'ResourceGroup'
  - The following properties are being added to the output type : 'ResourceGroupName'

## Az.SignalR

### `Get-AzSignalR`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.SignalR.Models.PSSignalRResource' is changing
  - The following properties in the output type are being deprecated : 'HostNamePrefix'
### `New-AzSignalR`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.SignalR.Models.PSSignalRResource' is changing
  - The following properties in the output type are being deprecated : 'HostNamePrefix'
### `Update-AzSignalR`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.SignalR.Models.PSSignalRResource' is changing
  - The following properties in the output type are being deprecated : 'HostNamePrefix'

## Az.Sql

### `Get-AzSqlDatabase`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Get-AzSqlDatabaseAdvancedThreatProtectionSetting`

- Cmdlet breaking-change will happen to all parameter set

  - The output type is changing from the existing type :'Microsoft.Azure.Commands.Sql.ThreatDetection.Model.DatabaseThreatDetectionPolicyModel' to the new type :'DatabaseAdvancedThreatProtectionSettingsModel'
### `Get-AzSqlDatabaseReplicationLink`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Replication.Model.AzureReplicationLinkModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Get-AzSqlInstance`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Get-AzSqlServerAdvancedThreatProtectionSetting`

- Cmdlet breaking-change will happen to all parameter set

  - The output type is changing from the existing type :'Microsoft.Azure.Commands.Sql.ThreatDetection.Model.ServerThreatDetectionPolicyModel' to the new type :'ServerAdvancedThreatProtectionSettingsModel'
### `New-AzSqlDatabase`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `New-AzSqlDatabaseCopy`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Replication.Model.AzureSqlDatabaseCopyModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `New-AzSqlDatabaseSecondary`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Replication.Model.AzureReplicationLinkModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `New-AzSqlInstance`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Remove-AzSqlDatabase`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Remove-AzSqlDatabaseSecondary`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Replication.Model.AzureReplicationLinkModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Remove-AzSqlInstance`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Set-AzSqlDatabase`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Database.Model.AzureSqlDatabaseModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Set-AzSqlDatabaseSecondary`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.Replication.Model.AzureReplicationLinkModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Set-AzSqlInstance`

- Cmdlet breaking-change will happen to all parameter set

  - The output type 'Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel' is changing
  - The following properties in the output type are being deprecated : 'BackupStorageRedundancy'
  - The following properties are being added to the output type : 'CurrentBackupStorageRedundancy' 'RequestedBackupStorageRedundancy'
### `Update-AzSqlDatabaseAdvancedThreatProtectionSetting`

- Parameter breaking-change will happen to all parameter sets
  - `-EmailAdmins`
    - The parameter : 'EmailAdmins' is changing.
  - `-ExcludedDetectionType`
    - The parameter : 'ExcludedDetectionType' is changing.
  - `-NotificationRecipientsEmails`
    - The parameter : 'NotificationRecipientsEmails' is changing.
  - `-RetentionInDays`
    - The parameter : 'RetentionInDays' is changing.
  - `-StorageAccountName`
    - The parameter : 'StorageAccountName' is changing.

### `Update-AzSqlServerAdvancedThreatProtectionSetting`

- Parameter breaking-change will happen to all parameter sets
  - `-EmailAdmins`
    - The parameter : 'EmailAdmins' is changing.
  - `-ExcludedDetectionType`
    - The parameter : 'ExcludedDetectionType' is changing.
  - `-NotificationRecipientsEmails`
    - The parameter : 'NotificationRecipientsEmails' is changing.
  - `-RetentionInDays`
    - The parameter : 'RetentionInDays' is changing.
  - `-StorageAccountName`
    - The parameter : 'StorageAccountName' is changing.

## Az.StorageSync

### `Set-AzStorageSyncServerEndpoint`

- Parameter breaking-change will happen to all parameter sets
  - `-InputObject`
    - Alias RegisteredServer is invalid and preserved for compatibility. Alias ServerEndpoint should be used instead

## Az.Websites

### `New-AzWebAppContainerPSSession`

- Cmdlet breaking-change will happen to all parameter set

  - The cmdlet is being deprecated. There will be no replacement for it.

## Az.SpringCloud

### `Get-AzSpringCloudApp`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to parameter set `GetAzSpringCloudApp_Get`
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Get-AzSpringCloudAppDeployment`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to parameter set `GetAzSpringCloudAppDeployment_Get`
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Get-AzSpringCloudAppResourceUploadUrl`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'

### `Get-AzSpringCloudOperation`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
### `Get-AzSpringCloudService`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `New-AzSpringCloudApp`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `New-AzSpringCloudAppDeployment`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `New-AzSpringCloudService`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Remove-AzSpringCloudApp`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to parameter set `RemoveAzSpringCloudApp_Delete`
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Remove-AzSpringCloudAppDeployment`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to parameter set `RemoveAzSpringCloudAppDeployment_Delete`
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Remove-AzSpringCloudService`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Restart-AzSpringCloudAppDeployment`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Start-AzSpringCloudAppDeployment`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Stop-AzSpringCloudAppDeployment`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to parameter set `StopAzSpringCloudAppDeployment_Stop`
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Update-AzSpringCloudApp`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to all parameter sets
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Update-AzSpringCloudAppDeployment`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to parameter set `UpdateAzSpringCloudAppDeployment_UpdateExpanded`
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'

### `Update-AzSpringCloudService`

- Cmdlet breaking-change will happen to all parameter set

  The cmdlet is being deprecated. There will be no replacement for it.
  - This change will take effect on '10/30/2022'
  - The change is expected to take effect from the version : '9.0.0'
- Parameter breaking-change will happen to parameter set `UpdateAzSpringCloudService_UpdateExpanded`
  - `-Name`
    - The parameter : 'Name' is changing.
    - This change will take effect on '10/30/2022'
    - The change is expected to take effect from the version : '9.0.0'