---
external help file: Microsoft.Azure.Commands.ServiceBus.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmServiceBusSubscription

## SYNOPSIS
Gets a subscription description for the specified topic.

## SYNTAX

```
Get-AzureRmServiceBusSubscription [-ResourceGroup] <String> [-NamespaceName] <String> [-TopicName] <String>
 [[-SubscriptionName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmServiceBusSubscription** cmdlet gets a subscription description for the specified Service Bus topic.

## EXAMPLES

### Example 1: Get a Service Bus subscription description
```
PS C:\> Get-AzureRmServiceBusSubscription -ResourceGroup "Default-ServiceBus-WestUS" -NamespaceName "SB-Example1" -TopicName "SB-Topic_example1" -SubscriptionName "SB-TopicSubscription-Example1"
```

This command gets a subscription description for the Service Bus topic named SB-TopicSubscription-Example1.

## PARAMETERS

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

### -SubscriptionName
Specifies the subscription name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopicName
Specifies the topic name.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### -ResourceGroup
 System.String
 

### -NamespaceName
 System.String
 

### -TopicName
 System.String
 

### -SubscriptionName
 System.String
 

## OUTPUTS

### Microsoft.Azure.Commands.ServiceBus.Models.SubscriptionAttributes
Name                                      : SB-TopicSubscription-Example1
Location                                  : West US
AccessedAt                                : 1/20/2017 3:18:54 AM
AutoDeleteOnIdle                          : 10675199.02:48:05.4775807
CountDetails                              : Microsoft.Azure.Management.ServiceBus.Models.MessageCountDetails
CreatedAt                                 : 1/20/2017 3:18:52 AM
DefaultMessageTimeToLive                  : 10675199.02:48:05.4775807
DeadLetteringOnFilterEvaluationExceptions : True
DeadLetteringOnMessageExpiration          : False
EnableBatchedOperations                   : True
EntityAvailabilityStatus                  : Available
IsReadOnly                                : 
LockDuration                              : 00:01:00
MaxDeliveryCount                          : 10
MessageCount                              : 0
RequiresSession                           : False
Status                                    : Active
UpdatedAt                                 : 1/20/2017 3:18:54 AM

## NOTES

## RELATED LINKS

[New-AzureRmServiceBusSubscription](./New-AzureRmServiceBusSubscription.md)

[Remove-AzureRmServiceBusSubscription](./Remove-AzureRmServiceBusSubscription.md)

[Set-AzureRmServiceBusSubscription](./Set-AzureRmServiceBusSubscription.md)
