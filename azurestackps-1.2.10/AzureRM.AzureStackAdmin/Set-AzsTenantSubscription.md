---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Set-AzsTenantSubscription

## SYNOPSIS
Updates the targeted user subscription while logged in as an administrator. An administrator can use this cmdlet to reassign or to suspend a user subscription.

## SYNTAX

```
Set-AzsTenantSubscription -Subscription <AdminSubscriptionDefinition> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The Set-AzsTenantSubscription cmdlet reassigns the currently logged user's subscription details.

## EXAMPLES

### Example 1
```
$subscriptionToUpdate = Get-AzsTenantSubscription
$subscriptionToUpdate.OfferId = "Abc123"
$subscriptionToUpdate.Owner = "<username for which you want to assign the subscription. For example: tenant2@msazurestack.onmicrosoft.com>" 
Set-AzsTenantSubscription -Subscription $subscriptionToUpdate
```

This example modifies the OfferId property of the current logged-in user's tenant subscription. The first statement gets the subscription and stores the object in the $subscriptionToUpdate variable. After the OfferId property is changed, the updated object is passed in the Subscription parameter of the Set-AzureRMTenantSubscription cmdlet.

### Example 2

```
$sub = Get-AzsTenantSubscription 
$sub.State ="Disabled" 
Set-AzsTenantSubscription -Subscription $sub 
```

By running the above example, an administrator can suspend an existing user subscription.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event. The following values are permitted for this object type.

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

### -Subscription
Updated subscription definition object.

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


