---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRMManagedSubscription

## SYNOPSIS
Updates the subscription of any tenant user.

## SYNTAX

```
Set-AzureRMManagedSubscription -Subscription <AdminSubscriptionDefinition>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRMManagedSubscription** cmdlet updates the subscription of any tenant user. The user must be logged in as a service administrator before issuing this cmdlet.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$subscriptionUpdated = Get-AzureRMManagedSubscription -TargetSubscriptionId "2fff214f-8589-4d25-b468-dc99320724bc"
$subscriptionUpdated.OfferId = "Abc123"
Set-AzureRMManagedSubscription -Subscription $subscriptionUpdated
```

This example modifies the **OfferId** property of a **SubscriptionDefinition** object and then passes the object in the **Subscription** parameter of the ** Set-AzureRMManagedSubscription** cmdlet.

## PARAMETERS

### -InformationAction
Not specified.

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
Not specified.

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
Not specified.

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

### -Subscription
Specifies an updated **AdminSubscriptionDefinition** object to be used for updating the existing subscription data.

```yaml
Type: AdminSubscriptionDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.AzureStack.Management.Models.SubscriptionDefinition

## OUTPUTS

### Microsoft.AzureStack.Management.Models.SubscriptionDefinition

## NOTES

## RELATED LINKS
