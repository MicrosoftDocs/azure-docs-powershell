---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Set-AzsSubscription

## SYNOPSIS
Modifies the current logged-in user's subscription.

## SYNTAX

```
Set-AzsSubscription -Subscription <SubscriptionDefinition> [-WhatIf] [-Confirm]
```

## DESCRIPTION
Modifies the current logged-in user's tenant subscription.

## EXAMPLES

### Example 1
```
Set-AzsSubscription -SubscriptionId $TenantSubscriptionId
```

### Example 2
```
$sub = Get-AzsSubscription 
$sub.State ="Disabled" 
Set-AzsSubscription -Subscription $sub 
```

The above example disables an unused user subscription.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subscription
Specifies an updated SubscriptionDefinition object to be used for updating the existing subscription data.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


