---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRMManagedSubscription

## SYNOPSIS
Gets details about the target subscription of the tenant user.

## SYNTAX

```
Get-AzureRMManagedSubscription [-TargetSubscriptionId <Guid>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRMManagedSubscription** cmdlet gets details about the target subscription of the tenant user. This cmdlet is useful to a service administrator. You must be logged in as service administrator before issuing this command.

## EXAMPLES

### Example 1: Get the details about the specified target subscription
```
Get-AzureRMManagedSubscription -TargetSubscriptionId "2fff214f-8589-4d25-b468-dc99320724bc"
```

This example gets the details about the target subscription that has the ID "2fff214f-8589-4d25-b468-dc99320724bc".

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa
Accepted values: SilentlyContinue, Stop, Continue, Inquire

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies a variable that is used for storing an informational message.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Specifies a variable that stores the value of the current pipeline element.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetSubscriptionId
The target subscription ID of the tenant user.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.AzureStack.Management.Models.SubscriptionDefinition

## NOTES

## RELATED LINKS
