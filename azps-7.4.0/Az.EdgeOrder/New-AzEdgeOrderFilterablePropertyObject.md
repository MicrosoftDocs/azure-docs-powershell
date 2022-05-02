---
external help file: 
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderFilterablePropertyObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderFilterablePropertyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderFilterablePropertyObject.md
---

# New-AzEdgeOrderFilterablePropertyObject

## SYNOPSIS
Create an in-memory object for FilterableProperty.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.edgeorder/new-azedgeorderfilterablepropertyobject) for up-to-date information.

## SYNTAX

```
New-AzEdgeOrderFilterablePropertyObject -SupportedValue <String[]> -Type <SupportedFilterTypes>
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for FilterableProperty.

## EXAMPLES

### Example 1: Filterable property object 
```powershell
$filterableProperty = New-AzEdgeOrderFilterablePropertyObject -Type "ShipToCountries" -SupportedValue @("US")
$filterableProperty | Format-List
```

```output
SupportedValue : {US}
Type           : ShipToCountries
```

ShipToCountries is mandatory filterable type, SupportedValue can be list of 2 letter valid ISO country codes.

## PARAMETERS

### -SupportedValue
Values to be filtered.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Type of product filter.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Support.SupportedFilterTypes
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.FilterableProperty

## NOTES

ALIASES

## RELATED LINKS
