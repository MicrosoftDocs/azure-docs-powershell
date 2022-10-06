---
title: Migration Guide for latest Az.ServiceBus PowerShell Module
description: This migration guide contains a list of breaking changes made to the Az.ServiceBus module in the Azure PowerShell 9.0.0 release.
ms.date: 08/25/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
---

# Migration Guide for latest Az.ServiceBus PowerShell Module

The `Az.ServiceBus` PowerShell module version 9.0.0 of Azure PowerShell that would be released in October introduces improvised cmdlets for public use.

These changes are focused towards making the PowerShell use seamless for the end users.

The following example installs the latest version of the `Az.ServiceBus` Azure PowerShell module.

```powershell
Install-Module -Name Az.ServiceBus -Repository PSGallery -Scope CurrentUser
```

## Major Changes:

### Behavior of -InputObject:

Until Module 8.3.0, -InputObject supports passing an in memory object to additional cmdlet in pipeline. Due to above design, updating resources becomes a multi step approach.

With the new module release, -InputObject parameter set would be changing for a seamless experience.

In contrast to earlier approach, -InputObject would now support object of corresponding input type as well as resource Id directly to the cmdlet. This would make cmdlet usage fairly easy and faster as compared to the old approach.

Below example shows the difference in -InputObject Usage:

### Before

Below example shows how to update queue properties on existing service bus namespace with Module version 8.3.0 or older

```
$QueueObj = Get-AzServiceBusQueue -ResourceGroup Default-ServiceBus-WestUS -NamespaceName SB-Example1 -QueueName SB-Queue_example1

$QueueObj.ForwardTo = "q1"
$QueueObj.ForwardDeadLetteredMessagesTo = "q1"
$QueueObj.DefaultMessageTimeToLive = "P1YT3H11M2S"

Set-AzServiceBusQueue -ResourceGroup Default-ServiceBus-WestUS -NamespaceName SB-Example1 -QueueName SB-Queue_example1 -InputObject $QueueObj
```

### After

Below example shows how to update queue properties starting with / after Module version  9.0.0

```
$queue = Get-AzServiceBusQueue -InputObject <ResourceID of ServiceBus Queue>

Set-AzServiceBusQueue -InputObject $queue -ForwardTo q1 -ForwardDeadLetteredMessagesTo q2 -DefaultMessageTimeToLive (New-Timespan -Days 365 -Hours 3 -Minutes 11 -Seconds 2)
```

- Input type of parameters `-DefaultMessageTimeToLive`, `-AutoDeleteOnIdle`, `-LockDuration`, `-DuplicateDetectionHistoryTimeWindow` has been changed from System.String to System.Timespan. Hence, ISO 8601 format for timespan can NO longer be fed as input to these parameters. Please use New-TimeSpan cmdlet object to construct Timespan variables as shown in the example above. Please refer [New-TimeSpan](/powershell/module/microsoft.powershell.utility/new-timespan) to know more about New-TimeSpan.

### Pipelining support

- Accept pipeline Input for InputObject (InputObject pipelining) can be implemented in the following manner:

```
Get-AzServiceBusQueue -InputObject <ResourceId of the queue> | Set-AzServiceBusQueue -MessageRetentionInDays 6
```

- Property pipelining would be disabled. In other words,  None of the cmdlet parameters apart from `-InputObject` would accept pipeline input.
- `-InputObject` parameter would no longer support parameter aliasing.

### Positional Binding

- Positional binding is not supported.

## Deprecation Announcements

With new release,below cmdlets are marked to be deprecated:

- Add-AzServiceBusIPRule
- Add-AzServiceBusVirtualNetworkRule
- Remove-AzServiceBusIPRule
- Remove-AzServiceBusVirtualNetworkRule
- Remove-AzServiceBusNetworkRuleSet

Use Set-AzServiceBusNetworkRuleSet to add/remove multiple IP/ virtual network rules.

## Changes to existing Cmdlets

## Network Rule Sets

### Set-AzServiceBusNetworkRuleSet

- Input type of parameter `-InputObject` and Output type of the cmdlet have been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSNetworkRuleSetAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.INetworkRuleSet`.
- Parameter `-IPRule` is changing type from `Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetIpRulesAttributes[]` to `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.INwRuleSetIPRules[]`.Please use `New-AzServiceBusIPRuleConfig` cmdlet to construct an in-memory object which can then be fed as input to `-IPRule`.
- Parameter `-VirtualNetworkRule` is changing type from `Microsoft.Azure.Commands.ServiceBus.Models.PSNWRuleSetVirtualNetworkRulesAttributes[]` to `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.INwRuleSetVirtualNetworkRules[]`.Please use `New-AzServiceBusVirtualNetworkRuleConfig` cmdlet to construct an in-memory object which can then be fed as input to `-VirtualNetworkRule`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided to `-InputObject` parameter.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- Parameter 'Name' has been replaced by 'NamespaceName'.

### Get-AzServiceBusNetworkRuleSet

- Input type of parameter `-InputObject` and Output type of the cmdlet have been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSNetworkRuleSetAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.INetworkRuleSet`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided to `-InputObject` parameter.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

## Authorization Rules and SAS Keys

### New-AzServiceBusAuthorizationRule

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbAuthorizationRule`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.
- Parameter 'Queue' has been renamed to 'QueueName'. 
- Parameter 'Topic' has been renamed to 'TopicName'

### Set-AzServiceBusAuthorizationRule

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbAuthorizationRule`.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- `-InputObject` parameter would no longer support alias `-AuthRuleObj`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.
- Parameter 'Queue' has been renamed to 'QueueName'. 
- Parameter 'Topic' has been renamed to 'TopicName'.

### Get-AzServiceBusAuthorizationRule

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSSharedAccessAuthorizationRuleAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbAuthorizationRule`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.
- Parameter 'Queue' has been renamed to 'QueueName'. 
- Parameter 'Topic' has been renamed to 'TopicName'.

### Remove-AzServiceBusAuthorizationRule

- Parameter 'Namespace' has been renamed to 'NamespaceName'.
- Parameter 'Queue' has been renamed to 'QueueName'. 
- Parameter 'Topic' has been renamed to 'TopicName'.



### New-AzServiceBusKey

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSListKeysAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IAccessKeys`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.
- Parameter 'Queue' has been renamed to 'QueueName'. 
- Parameter 'Topic' has been renamed to 'TopicName'

### Get-AzServiceBusKey

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSListKeysAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IAccessKeys`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.
- Parameter 'Queue' has been renamed to 'QueueName'. 
- Parameter 'Topic' has been renamed to 'TopicName'

## Queue Entity

### New-AzServiceBusQueue

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbQueue`.
- `-SizeInBytes` and `-MessageCount` are readonly parameters and are getting removed.
- Parameter `-EnableBatchedOperations` is renamed to `-EnableBatchedOperation`.
- Input type of parameters `-DefaultMessageTimeToLive`, `-AutoDeleteOnIdle`, `-LockDuration`, `-DuplicateDetectionHistoryTimeWindow` has been changed from System.String to System.Timespan. Hence, ISO 8601 format for timespan can NO longer be fed as input to these parameters. Please use New-TimeSpan cmdlet object to construct Timespan variables. Please refer [New-TimeSpan](/powershell/module/microsoft.powershell.utility/new-timespan) to know more about New-TimeSpan.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### Set-AzServiceBusQueue

- Input type of parameter `-InputObject` and  of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbQueue`.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- `-InputObject` parameter would no longer support alias `-QueueObj`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### Remove-AzServiceBusQueue

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbQueue`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### Get-AzServiceBusQueue

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSQueueAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbQueue`.
- Parameter `-MaxCount` has been removed. Use `-Skip` and `-Top` for pagination use cases.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

## Topic Entity

### Get-AzServiceBusTopic

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbTopic`.
- Parameter `-MaxCount` has been removed. Use `-Skip` and `-Top` for pagination use cases.
- Parameter `-ResourceGroupName` would no longer support alias `-ResourceGroup`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

### Set-AzServiceBusTopic

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbTopic`.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- `-InputObject` parameter would no longer support alias `-TopicObj`.
- Parameter `-ResourceGroupName` would no longer support alias `-ResourceGroup`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

### New-AzServiceBusTopic

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbTopic`.
-  `-SizeInBytes` is readonly parameter and is getting removed.
- Parameter `-EnableBatchedOperations` would be renamed to `-EnableBatchedOperation`.
- Input type of parameters `-DefaultMessageTimeToLive`, `-AutoDeleteOnIdle`, `-DuplicateDetectionHistoryTimeWindow` has been changed from System.String to System.Timespan. Hence, ISO 8601 format for timespan can NO longer be fed as input to these parameters. Please use New-TimeSpan cmdlet object to construct Timespan variables. Please refer [New-TimeSpan](/powershell/module/microsoft.powershell.utility/new-timespan) to know more about New-TimeSpan.
- Parameter `-ResourceGroupName` would no longer support alias `-ResourceGroup`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

### Remove-AzServiceBusTopic

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSTopicAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbTopic`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Parameter `-ResourceGroupName` would no longer support alias `-ResourceGroup`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

## Rule Entity

### Get-AzServiceBusRule

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSRulesAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IRule`.
- Parameter `-MaxCount` has been removed. Use `-Skip` and `-Top` for pagination use cases.
- Parameter 'Namespace' has been renamed to 'NamespaceName'. 
- Parameter 'Topic' has been renamed to 'TopicName'. 
- Parameter 'Subscription' has been renamed to 'SubscriptionName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### Set-AzServiceBusRule

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSRulesAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IRule`.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- Parameter 'Namespace' has been renamed to 'NamespaceName'. 
- Parameter 'Topic' has been renamed to 'TopicName'. 
- Parameter 'Subscription' has been renamed to 'SubscriptionName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### New-AzServiceBusRule

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSRulesAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IRule`.
- Parameter `-RequiresPreprocessing` is being renamed to `-ActionRequiresPreprocessing`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'. 
- Parameter 'Topic' has been renamed to 'TopicName'. 
- Parameter 'Subscription' has been renamed to 'SubscriptionName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### Remove-AzServiceBusRule

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSRulesAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IRule`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Parameter 'Namespace' has been renamed to 'NamespaceName'. 
- Parameter 'Topic' has been renamed to 'TopicName'. 
- Parameter 'Subscription' has been renamed to 'SubscriptionName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

## Subscription Entity

### Get-AzServiceBusSubscription

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbSubscription`.
- Parameter `-MaxCount` has been removed. Use `-Skip` and `-Top` for pagination use cases.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.  
- Parameter 'Topic' has been removed to 'TopicName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### New-AzServiceBusSubscription

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbSubscription`.
- Input type of parameters `-DefaultMessageTimeToLive`, `-AutoDeleteOnIdle`, `-LockDuration`, `-DuplicateDetectionHistoryTimeWindow` has been changed from System.String to System.Timespan. Hence, ISO 8601 format for timespan can NO longer be fed as input to these parameters. Please use New-TimeSpan cmdlet object to construct Timespan variables. Please refer [New-TimeSpan](/powershell/module/microsoft.powershell.utility/new-timespan) to know more about New-TimeSpan.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.  
- Parameter 'Topic' has been removed to 'TopicName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### Set-AzServiceBusSubscription

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbSubscription`.
- `-InputObject` parameter set would have a change in behaviour. Refer the [section](#behavior-of--inputobject) to know more.
- `-InputObject` parameter would no longer support alias `-SubscriptionObj`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.  
- Parameter 'Topic' has been removed to 'TopicName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

### Remove-AzServiceBusSubscription

- Input type of parameter `-InputObject` and Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSSubscriptionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ISbSubscription`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.  
- Parameter 'Topic' has been removed to 'TopicName'.  
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

## Private Endpoints

### Approve-AzServiceBusPrivateEndpointConnection

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusPrivateEndpointConnectionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IPrivateEndpointConnection`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Deny-AzServiceBusPrivateEndpointConnection

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusPrivateEndpointConnectionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IPrivateEndpointConnection`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Remove-AzServiceBusPrivateEndpointConnection

- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

### Get-AzServiceBusPrivateEndpointConnection

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusPrivateEndpointConnectionAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IPrivateEndpointConnection`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.

## Private Links

### Get-AzServiceBusPrivateLink

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusPrivateLinkResourceAttributes[]` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IPrivateLinkResourcesListResult`.

## Disaster Recovery Configs

### Get-AzServiceBusGeoDRConfiguration

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSNamespaceAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IArmDisasterRecovery`.
- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IArmDisasterRecovery`.
- `-Name` parameter would be removed from `-InputObject` parameter set. Henceforth,`-InputObject` must  contain the ResourceId  of  Disaster Recovery Configuration alias.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

### New-AzServiceBusGeoDRConfiguration

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IArmDisasterRecovery`.
-  `-InputObject` and `-ResourceId` are not supported during resource creation, hence are being removed.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

### Remove-AzServiceBusGeoDRConfiguration

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IArmDisasterRecovery`.
- `-ResourceId` parameter would be deprecated. Henceforth, resource id can be provided as input to `-InputObject` parameter.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

### Set-AzServiceBusGeoDRConfigurationBreakPair

- Parameter `-ResourceId` is being removed. Henceforth, resource id can be provided as input to `-InputObject`.
- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IArmDisasterRecovery`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'. 
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.
  

### Set-AzServiceBusGeoDRConfigurationFailOver

- Parameter `-ResourceId` is being removed. Henceforth, resource id can be provided as input to `-InputObject`.
- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IArmDisasterRecovery`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'.

## Migration Configurations

### Complete-AzServiceBusMigration

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IMigrationConfigProperties`.
- Parameter `-ResourceId` is being removed. Henceforth, resource id can be provided as input to `-InputObject`.
- Parameter 'Name' has been replaced by 'NamespaceName'.

### Get-AzServiceBusMigration

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusMigrationConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IMigrationConfigProperties`.
- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusMigrationConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IMigrationConfigProperties`.
- Parameter 'Name' has been replaced by 'NamespaceName'.

### Start-AzServiceBusMigration

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusMigrationConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IMigrationConfigProperties`.
- Parameter 'Name' has been replaced by 'NamespaceName'.

### Remove-AzServiceBusMigration

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IMigrationConfigProperties`.
- Parameter 'Name' has been replaced by 'NamespaceName'.

### Stop-AzServiceBusMigration

- Input type of parameter `-InputObject` has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSServiceBusDRConfigurationAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.IMigrationConfigProperties`.
- Parameter `-ResourceId` is being removed. Henceforth, resource id can be provided as input to `-InputObject`.
- Parameter 'Name' has been renamed to 'NamespaceName'
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.

## CheckNameAvailability

### Test-AzServiceBusName

- Output type of the cmdlet has been changed from `Microsoft.Azure.Commands.ServiceBus.Models.PSCheckNameAvailabilityResultAttributes` to
  `Microsoft.Azure.PowerShell.Cmdlets.ServiceBus.Models.Api202201Preview.ICheckNameAvailabilityResult`.
- Parameter 'Namespace' has been renamed to 'NamespaceName'. 
- Parameter 'ResourceGroupName' would no longer support alias 'ResourceGroup'.
