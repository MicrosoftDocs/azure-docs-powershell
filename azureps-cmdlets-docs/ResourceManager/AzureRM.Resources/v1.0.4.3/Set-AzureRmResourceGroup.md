---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmResourceGroup

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### Lists the resource group based in the name. (Default)
```
Set-AzureRmResourceGroup -Name <String> [-Tag] <Hashtable[]> [<CommonParameters>]
```

### Lists the resource group based in the Id.
```
Set-AzureRmResourceGroup [-Tag] <Hashtable[]> -Id <String> [<CommonParameters>]
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

### -Id
The resource group Id.

```yaml
Type: String
Parameter Sets: Lists the resource group based in the Id.
Aliases: ResourceGroupId, ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The resource group name.

```yaml
Type: String
Parameter Sets: Lists the resource group based in the name.
Aliases: ResourceGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
An array of hashtables which represents resource tags.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: Tags

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
System.Collections.Hashtable[]

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.PSResourceGroup

## NOTES

## RELATED LINKS

