---
external help file: Az.Cdn-help.xml
Module Name: Az.Cdn
online version: https://learn.microsoft.com/powershell/module/Az.Cdn/new-azcdndeliveryruleresponseheaderactionobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzCdnDeliveryRuleResponseHeaderActionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzCdnDeliveryRuleResponseHeaderActionObject.md
---

# New-AzCdnDeliveryRuleResponseHeaderActionObject

## SYNOPSIS
Create an in-memory object for DeliveryRuleResponseHeaderAction.

## SYNTAX

```
New-AzCdnDeliveryRuleResponseHeaderActionObject -ParameterHeaderAction <String> -ParameterHeaderName <String>
 -ParameterTypeName <String> [-ParameterValue <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for DeliveryRuleResponseHeaderAction.

## EXAMPLES

### Example 1: Create an in-memory object for AzureCDN DeliveryRuleResponseHeaderAction
```powershell
New-AzCdnDeliveryRuleResponseHeaderActionObject -Name ModifyResponseHeader -ParameterHeaderAction Append -ParameterHeaderName a1 -ParameterValue a1
```

```output
Name
----
ModifyResponseHeader
```

Create an in-memory object for AzureCDN DeliveryRuleResponseHeaderAction

## PARAMETERS

### -ParameterHeaderAction
Action to perform.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterHeaderName
Name of the header to modify.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterTypeName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterValue
Value for the specified action.

```yaml
Type: System.String
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.DeliveryRuleResponseHeaderAction

## NOTES

## RELATED LINKS
