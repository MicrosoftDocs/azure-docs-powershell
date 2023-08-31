---
description: This migration guide contains a list of breaking changes made to the Az.EventHub module in the Azure PowerShell 9.0.1 release.
ms.custom: devx-track-azurepowershell
ms.date: 08/01/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Migration Guide for latest Az.EventHub PowerShell Module
---

# Migration Guide for latest Az.EventHub PowerShell Module

The `Az.EventHub` PowerShell module version 9.0.1 of Azure PowerShell that would be released in October introduces improvised cmdlets for public use.

These changes are focused towards making the PowerShell use more productive and seamless for the end users.

The following example installs the latest version of the `Az.Eventhub` Azure PowerShell module.

```powershell
Install-Module -Name Az.EventHub -Repository PSGallery -Scope CurrentUser
```

## Major Changes:

### Behavior of -InputObject:

Until Module 8.3.0, -InputObject supports passing an in memory object to additional cmdlet in pipeline. Due to above design, updating resources becomes a multi step approach.

With the new module release, -InputObject parameter set would be changing for a seamless experience.

In contrast to earlier approach, -InputObject would now support object of corresponding input type as well as resource Id directly to the cmdlet. This would make cmdlet usage fairly easy and faster as compared to the old approach.

Below example shows the difference in -InputObject Usage:

### Before

Below example shows how to update capture description on existing event hub with Module version 8.3.0 or older

```
$createdEventHub = Get-AzEventHub -ResourceGroupName MyResourceGroupName -Namespace MyNamespaceName -Name MyCreatedEventHub
$createdEventHub.CaptureDescription = New-Object -TypeName Microsoft.Azure.Commands.EventHub.Models.PSCaptureDescriptionAttributes
$createdEventHub.CaptureDescription.Enabled = $true
$createdEventHub.CaptureDescription.IntervalInSeconds  = 120
$createdEventHub.CaptureDescription.Encoding  = "Avro"
$createdEventHub.CaptureDescription.SizeLimitInBytes = 10485763
$createdEventHub.CaptureDescription.Destination.Name = "EventHubArchive.AzureBlockBlob"
$createdEventHub.CaptureDescription.Destination.BlobContainer = "container"
$createdEventHub.CaptureDescription.Destination.ArchiveNameFormat = "{Namespace}/{EventHub}/{PartitionId}/{Year}/{Month}/{Day}/{Hour}/{Minute}/{Second}"
$createdEventHub.CaptureDescription.Destination.StorageAccountResourceId = "/subscriptions/{SubscriptionId}/resourceGroups/MyResourceGroupName/providers/Microsoft.ClassicStorage/storageAccounts/teststorage"
Set-AzEventHub -ResourceGroupName MyResourceGroupName -Namespace MyNamespaceName -Name MyEventHubName -InputObject $createdEventHub
```

### After

Below example shows how to update capture description on existing event hub with starting with / after Module version  9.0.1

```
$eventhub = Get-AzEventHub -InputObject <ResourceID of event hub>

Set-AzEventHub -InputObject $eventhub -CaptureEnabled -SizeLimitInBytes 10485763 -IntervalInSeconds 120 -Encoding Avro -DestinationName EventHubArchive.AzureBlockBlob -BlobContainer container -ArchiveNameFormat "{Namespace}/{EventHub}/{PartitionId}/{Year}/{Month}/{Day}/{Hour}/{Minute}/{Second}" -StorageAccountResourceId "/subscriptions/{SubscriptionId}/resourceGroups/MyResourceGroupName/providers/Microsoft.ClassicStorage/storageAccounts/teststorage"

```

### Pipelining support

- Accept pipeline Input for InputObject (InputObject pipelining) can be implemented in the following manner:

```
Get-AzEventHub -InputObject <ResourceId of the eventhub> | Set-AzEventHub -MessageRetentionInDays 6
```

- Property pipelining would be disabled. In other words, none of the cmdlet parameters apart from `-InputObject` would accept pipeline input.
- `-InputObject` parameter would no longer support parameter aliasing.

### Positional Binding

- Positional binding is not supported.

## Deprecation Announcements

With new release,below cmdlets are marked to be deprecated:

- Add-AzEventHubIPRule
- Add-AzEventHubVirtualNetworkRule
- Remove-AzEventHubIPRule
- Remove-AzEventHubVirtualNetworkRule
- Remove-AzEventHubNetworkRuleSet

Use Set-AzEventHubNetworkRuleSet to add/remove IP or virtual network rules.

## Changes to existing cmdlets

Below list talks about the changes to existing cmdlets in detailed manner:

## Application Groups

### Get-AzEventHubApplicationGroup

- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IApplicationGroup`.

### New-AzEventHubApplicationGroup

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IApplicationGroup`.
- `-ThrottlingPolicyConfig` would be renamed to `-Policy` and type would change from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubThrottlingPolicyConfigAttributes[]` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IApplicationGroupPolicy[]`. New-AzEventHubThrottlingPolicyConfig can still be used to construct this object.

### Set-AzEventHubApplicationGroup

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IApplicationGroup`.
- `-ThrottlingPolicyConfig` would be renamed to `-Policy` and type would change from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubThrottlingPolicyConfigAttributes[]` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IApplicationGroupPolicy[]`. New-AzEventHubThrottlingPolicyConfig can still be used to construct this object.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### New-AzEventHubThrottlingPolicyConfig

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubThrottlingPolicyConfigAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IThrottlingPolicy`.

### Remove-AzEventHubApplicationGroup

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubApplicationGroupAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IApplicationGroup`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

## Network Rule Sets

### Set-AzEventHubNetworkRuleSet

- Input type of parameter `-InputObject` and Output type has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSNetworkRuleSetAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.INetworkRuleSet`.
- Parameter `-IPRule` is changing type from `Microsoft.Azure.Commands.EventHub.Models.PSNWRuleSetIpRulesAttributes[]` to `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.INwRuleSetIPRules[]`. Please use `New-AzEventHubIPRuleConfig` cmdlet to construct an in-memory object which can be fed as input to `-IPRule`.
- Parameter `-VirtualNetworkRule` is changing type from `Microsoft.Azure.Commands.EventHub.Models.PSNWRuleSetVirtualNetworkRulesAttributes[]` to `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.INwRuleSetVirtualNetworkRules[]`. Please use `New-AzEventHubVirtualNetworkRuleConfig` cmdlet to construct an in-memory object which can then be fed as input to `-VirtualNetworkRule`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided to `-InputObject` parameter.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.

### Get-AzEventHubNetworkRuleSet

- Output type has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSNetworkRuleSetAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.INetworkRuleSet`.

## Authorization Rules and SAS Keys

### New-AzEventHubAuthorizationRule

- Output type has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSSharedAccessAuthorizationRuleAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IAuthorizationRule`.

### Set-AzEventHubAuthorizationRule

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSSharedAccessAuthorizationRuleAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IAuthorizationRule`.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- `-InputObject` parameter would no longer support alias `-AuthRuleObj`.

### Get-AzEventHubAuthorizationRule

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSSharedAccessAuthorizationRuleAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IAuthorizationRule`.

### New-AzEventHubKey

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSListKeysAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IAccessKeys`.
- Parameter `-ResourceGroupName` would no longer support alias `-ResourceGroup`.

### Get-AzEventHubKey

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSListKeysAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IAccessKeys`.

## Consumer Groups

### New-AzEventHubConsumerGroup

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSConsumerGroupAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IConsumerGroup`.

### Set-AzEventHubConsumerGroup

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSConsumerGroupAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IConsumerGroup`.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.

### Get-AzEventHubConsumerGroup

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSConsumerGroupAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IConsumerGroup`.
- Parameter `-MaxCount` has been removed. Use `-Skip` and `-Top`  pagination use case.

### Remove-AzEventHubConsumerGroup

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSConsumerGroupAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IConsumerGroup`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

## Clusters

### New-AzEventHubCluster

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubClusterAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.ICluster`.
- `-ResourceId` would be removed as it is not supported for Creation operation and is available for use after resource is created.

### Set-AzEventHubCluster

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubClusterAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.ICluster`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.

### Get-AzEventHubCluster

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubClusterAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.ICluster`.

### Remove-AzEventHubCluster

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubClusterAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.ICluster`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.


### Get-AzEventHubClustersAvailableRegion

 - Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.
PSEventHubsAvailableCluster[]` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IAvailableCluster`.

## EventHub

### New-AzEventHub

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IEventhub`.
- `-InputObject` would be removed as it is not supported for Creation operation and is available for use after resource is created.

### Set-AzEventHub

- Input type of parameter `-InputObject` and output type of the cmdlet have been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IEventhub`. CaptureDescription class data members would be flattened and would directly be accessible as data members within Microsoft.`Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IEventhub`. Please refer to example on top to know more.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- `-InputObject` parameter would no longer support alias `-EventHubObj`.

### Remove-AzEventHub

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IEventhub`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Get-AzEventHub

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IEventhub`.
- Parameter `-MaxCount` has been removed. Use `-Skip` and `-Top`  for pagination use case.
- Parameter `-NamespaceObject` is being replaced by `-InputObject` of type `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IEventhub`.

## Private Endpoints

### Approve-AzEventHubPrivateEndpointConnection

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubPrivateEndpointConnectionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IPrivateEndpointConnection`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Deny-AzEventHubPrivateEndpointConnection

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubPrivateEndpointConnectionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IPrivateEndpointConnection`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Remove-AzEventHubPrivateEndpointConnection

- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Get-AzEventHubPrivateEndpointConnection

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubPrivateEndpointConnectionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IPrivateEndpointConnection`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

## Private Links

### Get-AzEventHubPrivateLink

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubPrivateLinkResourceAttributes[]` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IPrivateLinkResourcesListResult`.

## Disaster Recovery Configs

### Get-AzEventHubGeoDRConfiguration

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IArmDisasterRecovery`.
- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IArmDisasterRecovery`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### New-AzEventHubGeoDRConfiguration

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IArmDisasterRecovery`.
-  `-InputObject` and `-ResourceId` are not supported during resource creation, hence are being removed.

### Remove-AzEventHubGeoDRConfiguration

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IArmDisasterRecovery`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Set-AzEventHubGeoDRConfigurationBreakPair

- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IArmDisasterRecovery`.

### Set-AzEventHubGeoDRConfigurationFailOver

- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.IArmDisasterRecovery`.

## Schema Groups

### New-AzEventHubSchemaGroup

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.ISchemaGroup`.

### Get-AzEventHubSchemaGroup

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.ISchemaGroup`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Remove-AzEventHubSchemaGroup

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.EventHub.Models.PSEventHubsSchemaRegistryAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.ISchemaGroup`.

## CheckNameAvailability

### Test-AzEventHubName

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.EventHub.Models.
PSCheckNameAvailabilityResultAttributes ` to
  `Microsoft.Azure.PowerShell.Cmdlets.EventHub.Models.Api202201Preview.ICheckNameAvailabilityResult`.
