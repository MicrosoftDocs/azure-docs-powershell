---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVMExtensionImage.md
schema: 2.0.0
---

# Get-AzureVMExtensionImageType

## SYNOPSIS
Gets the type of an Azure extension.

## SYNTAX

```
Get-AzureVMExtensionImageType -Location <String> -PublisherName <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMExtensionImageType** cmdlet gets the type of an Azure extension.

## EXAMPLES

### Example 1: Get an extension image type
```
PS C:\>Get-AzureVMExtensionImageType -Location "Central US" -PublisherName "Fabrikam"
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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublisherName
Specifies the name of a publisher of an extension.
To obtain an extension publisher, use the **Get-AzureVMImagePublisher** cmdlet.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVMExtensionImage](.\Get-AzureVMExtensionImage.md)

