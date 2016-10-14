---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureRmVMExtensionImage.md
schema: 2.0.0
---

# Get-AzureRmVMExtensionImageType

## SYNOPSIS
Gets the type of an azure_2 extension.

## SYNTAX

```
Get-AzureRmVMExtensionImageType -Location <String> -PublisherName <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmVMExtensionImageType** cmdlet gets the type of an azure_2 extension.

## EXAMPLES

### Example 1: Get an extension image type
```
PS C:\>Get-AzureRmVMExtensionImageType -Location "Central US" -PublisherName "Fabrikam"
```

This command gets the extension image type for the specified publisher and location.

## PARAMETERS

### -Location
Specifies the location of an extension.
This cmdlet gets the type for an extension at the location that this parameter specifies.

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

### -PublisherName
Specifies the name of a publisher of an extension.
To obtain an extension publisher, use the Get-AzureRmVMImagePublisher cmdlet.
This cmdlet gets the type for an extension from the publisher that this parameter specifies.

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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

## RELATED LINKS

[Get-AzureRmVMExtensionImage](.\Get-AzureRmVMExtensionImage.md)

[Get-AzureRmVMImagePublisher](.\Get-AzureRmVMImagePublisher.md)

