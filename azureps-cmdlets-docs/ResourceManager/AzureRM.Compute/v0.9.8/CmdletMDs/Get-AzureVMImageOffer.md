---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVMImage.md
schema: 2.0.0
---

# Get-AzureVMImageOffer

## SYNOPSIS
Gets VMImage offer types.

## SYNTAX

```
Get-AzureVMImageOffer -Location <String> -PublisherName <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMImageOffer** cmdlet gets the **VMImage** offer types.

## EXAMPLES

### Example 1: Get offer types for a publisher
```
PS C:\>Get-AzureVMImageOffer -Location "Central US" -PublisherName "Fabrikam"
```

This command gets the offer types for the specified publisher in the Central US region.

## PARAMETERS

### -Location
Specifies the location of the **VMImage**.

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
Specifies the name of a publisher of a **VMImage**.
To obtain a publisher, use the **Get-AzureVMImagePublisher** cmdlet.

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

[Get-AzureVMImage](.\Get-AzureVMImage.md)

[Get-AzureVMImagePublisher](.\Get-AzureVMImagePublisher.md)

[Get-AzureVMImageSku](.\Get-AzureVMImageSku.md)

[Save-AzureVMImage](.\Save-AzureVMImage.md)

