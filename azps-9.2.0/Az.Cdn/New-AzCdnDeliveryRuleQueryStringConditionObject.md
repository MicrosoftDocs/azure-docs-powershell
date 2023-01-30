---
external help file: 
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzCdnDeliveryRuleQueryStringConditionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnDeliveryRuleQueryStringConditionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnDeliveryRuleQueryStringConditionObject.md
---

# New-AzCdnDeliveryRuleQueryStringConditionObject

## SYNOPSIS
Create an in-memory object for DeliveryRuleQueryStringCondition.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.cdn/new-azcdndeliveryrulequerystringconditionobject) for up-to-date information.

## SYNTAX

```
New-AzCdnDeliveryRuleQueryStringConditionObject -Name <MatchVariable> -ParameterOperator <QueryStringOperator>
 [-ParameterMatchValue <String[]>] [-ParameterNegateCondition <Boolean>] [-ParameterTransform <Transform[]>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for DeliveryRuleQueryStringCondition.

## EXAMPLES

### Example 1: Create an in-memory object for AzureCDN DeliveryRuleQueryStringCondition
```powershell
New-AzCdnDeliveryRuleQueryStringConditionObject -Name QueryString -ParameterOperator Equal -ParameterMatchValue test -ParameterNegateCondition $False -ParameterTransform Lowercase
```

```output
Name
----
QueryString
```

Create an in-memory object for AzureCDN DeliveryRuleQueryStringCondition

## PARAMETERS

### -Name
The name of the condition for the delivery rule.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.MatchVariable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterMatchValue
The match value for the condition of the delivery rule.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterNegateCondition
Describes if this is negate condition or not.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterOperator
Describes operator to be matched.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.QueryStringOperator
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterTransform
List of transforms.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.Transform[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.DeliveryRuleQueryStringCondition

## NOTES

ALIASES

## RELATED LINKS
