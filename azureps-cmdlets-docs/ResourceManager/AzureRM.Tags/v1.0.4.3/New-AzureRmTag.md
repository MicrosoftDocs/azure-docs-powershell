---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmTag

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

```
New-AzureRmTag [-Name] <String> [[-Value] <String>] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Name
Name of the tag.
If the tag name doesn't exist, create the tag name.
Otherwise, add the value to the existing tag name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Value of the tag.
If specified, add the tag value to the tag name.
Otherwise, keep the tag value unchanged.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Tags.Model.PSTag

## NOTES

## RELATED LINKS

