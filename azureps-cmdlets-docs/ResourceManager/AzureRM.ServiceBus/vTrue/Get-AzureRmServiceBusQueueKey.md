---
external help file: Microsoft.Azure.Commands.ServiceBus.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmServiceBusQueueKey

## SYNOPSIS
Gets the primary and secondary connection strings for the given Service Bus queue.

## SYNTAX

```
Get-AzureRmServiceBusQueueKey [-ResourceGroup] <String> [-NamespaceName] <String> [-QueueName] <String>
 [-AuthorizationRuleName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmServiceBusQueueKey** cmdlet gets the primary and secondary connection strings for the given Service Bus queue. 

## EXAMPLES

### Example 1: Get the primary and secndary connection strings for a Service Bus queue
```
PS C:\> Get-AzureRmServiceBusQueueKey -ResourceGroup "Default-ServiceBus-WestUS" -NamespaceName "SB-Example1" -QueueName "SB-Queue_example1" -AuthorizationRuleName "SBAuthoRule1"
```

This command gets the primary and secondary connection strings for the Service Bus queue named SB-Queue_example1.

## PARAMETERS

### -AuthorizationRuleName
Specifies the name of the queue authorization rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
Specifies the name of the Service Bus queue.

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

### Microsoft.Azure.Commands.ServiceBus.Models.ListKeysAttributes
PrimaryConnectionString   : Endpoint=sb://sb-example1.servicebus.windows.net/;SharedAccessKeyName=SBAuthoRule1;SharedAccessKey={SharedAccessKey-value};EntityPath=SB-Queue_e
                            xampl1
SecondaryConnectionString : Endpoint=sb://sb-example1.servicebus.windows.net/;SharedAccessKeyName=SBAuthoRule1;SharedAccessKey={SharedAccessKey-value};EntityPath=SB-Queue_e
                            xampl1
PrimaryKey                : {PrimaryKey value}
SecondaryKey              : {SecondaryKey value}
KeyName                   : SBAuthoRule1

## NOTES

## RELATED LINKS

[New-AzureRmServiceBusQueueKey](./New-AzureRmServiceBusQueueKey.md)
