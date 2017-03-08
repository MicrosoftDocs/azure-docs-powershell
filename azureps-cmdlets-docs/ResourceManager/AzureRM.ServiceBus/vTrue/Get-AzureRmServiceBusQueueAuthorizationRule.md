---
external help file: Microsoft.Azure.Commands.ServiceBus.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmServiceBusQueueAuthorizationRule

## SYNOPSIS
Gets the description of a specified authorization rule for a given Service Bus queue. 

## SYNTAX

```
Get-AzureRmServiceBusQueueAuthorizationRule [-ResourceGroup] <String> [-NamespaceName] <String>
 [-QueueName] <String> [[-AuthorizationRuleName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmServiceBusQueueAuthorizationRule** cmdlet gets the description of a specified authorization rule on the given Service Bus queue.

## EXAMPLES

### Example 1: Get an authorization rule description from a Service Bus queue
```
PS C:\> Get-AzureRmServiceBusQueueAuthorizationRule -ResourceGroup "Default-ServiceBus-WestUS" -NamespaceName "SB-Example1" -QueueName "SB-Queue_example1" -AuthorizationRuleName "SBAuthoRule1"
```

This command gets the authorization rule description from the authorization rule named SBAuthoRule1 for the Service Bus queue named SB-Queue_example1.

## PARAMETERS

### -AuthorizationRuleName
Specifies the name of the authorization rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NamespaceName
Specifies the name of the Service Bus namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -QueueName
Specifies the name of the queue.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Specifies the name of the resource group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### -ResourceGroup
 System.String
 

### -NamespaceName
 System.String
 

### -QueueName
 System.String
 

### -AuthorizationRuleName
 System.String

## OUTPUTS

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.ServiceBus.Models.SharedAccessAuthorizationRuleAttributes, Microsoft.Azure.Commands.ServiceBus, Version=0.0.1.0, Culture=neutral, PublicKeyToken=null]]
Id       : /subscriptions/854d368f-1828-428f-8f3c-f2affa9b2f7d/resourceGroups/Default-ServiceBus-WestUS/providers/Microsoft.ServiceBus/namespaces/SB-Example1/queues/SB-Queue_exampl1/authorizati
           onRules/SBAuthoRule1
Type     : Microsoft.ServiceBus/AuthorizationRules
Name     : SBAuthoRule1
Location : West US
Tags     : 
Rights   : {Listen, Send}

## NOTES

## RELATED LINKS

[New-AzureRmServiceBusQueueAuthorizationRule](./New-AzureRmServiceBusQueueAuthorizationRule.md)

[Remove-AzureRmServiceBusQueueAuthorizationRule](./Remove-AzureRmServiceBusQueueAuthorizationRule.md)

[Set-AzureRmServiceBusQueueAuthorizationRule](./Set-AzureRmServiceBusQueueAuthorizationRule.md)
