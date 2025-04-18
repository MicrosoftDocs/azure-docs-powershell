---
external help file: Az.EventGrid-help.xml
Module Name: Az.EventGrid
online version: https://learn.microsoft.com/powershell/module/Az.EventGrid/new-azeventgridnumberinrangeadvancedfilterobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridNumberInRangeAdvancedFilterObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/New-AzEventGridNumberInRangeAdvancedFilterObject.md
---

# New-AzEventGridNumberInRangeAdvancedFilterObject

## SYNOPSIS
Create an in-memory object for NumberInRangeAdvancedFilter.

## SYNTAX

```
New-AzEventGridNumberInRangeAdvancedFilterObject [-Value <Double[][]>] [-Key <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for NumberInRangeAdvancedFilter.

## EXAMPLES

### Example 1: Create an in-memory object for NumberInRangeAdvancedFilter.
```powershell
$valuesObj = @(11.11, 22.22, 33.33, 44.44)
New-AzEventGridNumberInRangeAdvancedFilterObject -Key "testKey" -Value @(,$valuesObj)
```

```output
Key     OperatorType
---     ------------
testKey NumberInRange
```

Create an in-memory object for NumberInRangeAdvancedFilter.

## PARAMETERS

### -Key
The field/property in the event based on which you want to filter.

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

### -Value
The set of filter values.

```yaml
Type: System.Double[][]
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

### Microsoft.Azure.PowerShell.Cmdlets.EventGrid.Models.NumberInRangeAdvancedFilter

## NOTES

## RELATED LINKS
