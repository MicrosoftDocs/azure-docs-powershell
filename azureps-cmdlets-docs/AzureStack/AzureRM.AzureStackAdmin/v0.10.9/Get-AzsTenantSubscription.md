---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Get-AzsTenantSubscription

## SYNOPSIS
This cmdlet enables service administrator to get the tenant target subscription id.

## SYNTAX

```
Get-AzsTenantSubscription [-SubscriptionId <Guid>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION
This cmdlet enables service administrator to get the tenant target subscription id

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-AzsTenantSubscription -SubscriptionId "2fff214f-8589-4d25-b468-dc99320724bc"
```

Description

-----------

The example gets the target subscription id.
Login as service administrator before issuing this command

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

### -SubscriptionId
The target subscription id of the tenant user.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: TargetSubscriptionId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

