---
external help file: Az.ActionGroup.psm1-help.xml
Module Name: Az.Monitor
online version: https://learn.microsoft.com/powershell/module/Az.Monitor/new-azactiongroupeventhubreceiverobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzActionGroupEventHubReceiverObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzActionGroupEventHubReceiverObject.md
---

# New-AzActionGroupEventHubReceiverObject

## SYNOPSIS
Create an in-memory object for EventHubReceiver.

## SYNTAX

```
New-AzActionGroupEventHubReceiverObject -EventHubName <String> -EventHubNameSpace <String> -Name <String>
 -SubscriptionId <String> [-TenantId <String>] [-UseCommonAlertSchema <Boolean>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for EventHubReceiver.

## EXAMPLES

### Example 1: create action group event hub receiver
```powershell
New-AzActionGroupEventHubReceiverObject -EventHubName "testEventHub" -EventHubNameSpace "testEventHubNameSpace" -Name "sample eventhub" -SubscriptionId "aaaa0a0a-bb1b-cc2c-dd3d-eeeeee4e4e4e" -TenantId "aaaabbbb-0000-cccc-1111-dddd2222eeee"
```

```output
EventHubName         : testEventHub
EventHubNameSpace    : testEventHubNameSpace
Name                 : sample eventhub
SubscriptionId       : aaaa0a0a-bb1b-cc2c-dd3d-eeeeee4e4e4e
TenantId             : aaaabbbb-0000-cccc-1111-dddd2222eeee
UseCommonAlertSchema :
```

This command creates action group event hub receiver object.

### Example 2: create another action group event hub receiver
```powershell
New-AzActionGroupEventHubReceiverObject -EventHubName "testEventHub" -EventHubNameSpace "actiongrouptest" -Name "sample eventhub" -SubscriptionId bbbb1b1b-cc2c-dd3d-ee4e-ffffff5f5f5f
```

```output
EventHubName         : testEventHub
EventHubNameSpace    : actiongrouptest
Name                 : sample eventhub
SubscriptionId       : bbbb1b1b-cc2c-dd3d-ee4e-ffffff5f5f5f
TenantId             : 
UseCommonAlertSchema :
```

This command creates another action group event hub receiver object.

## PARAMETERS

### -EventHubName
The name of the specific Event Hub queue.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventHubNameSpace
The Event Hub namespace.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the Event hub receiver.
Names must be unique across all receivers within an action group.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The Id for the subscription containing this event hub.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TenantId
The tenant Id for the subscription containing this event hub.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseCommonAlertSchema
Indicates whether to use common alert schema.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Monitor.ActionGroup.Models.EventHubReceiver

## NOTES

## RELATED LINKS
