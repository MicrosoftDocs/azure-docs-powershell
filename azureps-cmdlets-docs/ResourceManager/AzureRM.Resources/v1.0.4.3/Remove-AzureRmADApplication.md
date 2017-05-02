---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmADApplication

## SYNOPSIS
Deletes the azure active directory application.

## SYNTAX

```
Remove-AzureRmADApplication -ApplicationObjectId <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

Deletes the azure active directory application.

## EXAMPLES

### --------------------------  Delete AAD application.  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> Remove-AzureRmADApplication -ApplicationObjectId b4cd1619-80b3-4cfb-9f8f-9f2333425738 -Force
```

Deletes the azure active directory application.

## PARAMETERS

### -ApplicationObjectId
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

[New-AzureRmADApplication]()

