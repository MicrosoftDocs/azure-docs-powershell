---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Remove-AzsTenantSubscription

## SYNOPSIS
The cmdlet Remove-AzsTenantSubscription is used by administrators to remove a user subscription.

## SYNTAX

```
Remove-AzsTenantSubscription -SubscriptionId <Guid> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The cmdlet Remove-AzsTenantSubscription is used by administrators to remove a user subscription.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Remove-AzsTenantSubscription -SubscriptionId "83a3cff6-b856-4db1-8d1b-86386ff9d515"
```

Description

-----------

The example deletes the specific subscription 83a3cff6-b856-4db1-8d1b-86386ff9d515.
This is executed after logging in to the azure stack environment as a service administrator.

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

### -SubscriptionId
Specifies the Subscription Id that needs to be removed.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: TargetSubscriptionId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

