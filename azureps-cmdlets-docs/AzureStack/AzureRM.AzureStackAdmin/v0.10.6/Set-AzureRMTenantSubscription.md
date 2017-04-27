---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRMTenantSubscription

## SYNOPSIS
Updates the current logged-in user's tenant subscription.

## SYNTAX

```
Set-AzureRMTenantSubscription -Subscription <SubscriptionDefinition> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRMTenantSubscription** cmdlet updates the current logged-in user's tenant subscription.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$subscriptionUpdated = Get-AzureRmTenantSubscription
$subscriptionUpdated.OfferId = "Abc123"
Set-AzureRMTenantSubscription -Subscription $subscriptionUpdated
```

This example modifies the **OfferId** property of a **SubscriptionDefinition** object and then passes the object in the **Subscription** parameter of the ** Set-AzureRMTenantSubscription** cmdlet.

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
Specifies an updated **SubscriptionDefinition** object to be used for updating the existing subscription data.

```yaml
Type: SubscriptionDefinition
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

### None

## OUTPUTS

### Microsoft.AzureStack.Management.Models.SubscriptionDefinition

## NOTES

## RELATED LINKS
