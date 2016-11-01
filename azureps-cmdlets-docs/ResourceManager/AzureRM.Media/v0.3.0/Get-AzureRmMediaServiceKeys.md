---
external help file: Microsoft.Azure.Commands.Media.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CF44604E-FD17-4E09-AEAA-50DE32CD55EC
---

# Get-AzureRmMediaServiceKeys

## SYNOPSIS
Gets key information for accessing the REST endpoint associated with the media service.

## SYNTAX

```
Get-AzureRmMediaServiceKeys [-ResourceGroupName] <String> [-AccountName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmMediaServiceKeys** cmdlet gets key information for accessing the Representational State Transfer (REST) endpoint associated with the Azure media service.

## EXAMPLES

### Example 1: Get the key information for accessing the media service
```
PS C:\>Get-AzureRmMediaServiceKeys -ResourceGroupName "ResourceGroup001" -AccountName "MediaService001"
```

This command gets the key information for accessing the media service named MediaService001 that belongs to the resource group named ResourceGroup001.

## PARAMETERS

### -ResourceGroupName
Specifies the name of the resource group that contains the media service.

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

### -AccountName
Specifies the name of the media service that this cmdlet gets the media service keys from.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name, ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureRmMediaServiceKey](./Set-AzureRmMediaServiceKey.md)


