---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVMImage.md
schema: 2.0.0
---

# Get-AzureVMImageSku

## SYNOPSIS
Gets VMImage SKUs.

## SYNTAX

```
Get-AzureVMImageSku -Location <String> -PublisherName <String> -Offer <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMImageSku** cmdlet gets **VMImage** SKUs.

## EXAMPLES

### Example 1: Get SKUs
```
PS C:\>Get-AzureVMImageSku -Location "Central US" -PublisherName "Fabrikam" -Offer "LinuxServer"
```

This command gets the SKUs for the specified publisher and offer.

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

### -Offer
Specifies the type of **VMImage** offer.
To obtain an image offer, use the Get-AzureVMImageOffer cmdlet.

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
Specifies the publisher of a **VMImage**.
To obtain an image publisher, use the Get-AzureVMImagePublisher cmdlet.

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

[Get-AzureVMImageOffer](.\Get-AzureVMImageOffer.md)

[Get-AzureVMImagePublisher](.\Get-AzureVMImagePublisher.md)

[Save-AzureVMImage](.\Save-AzureVMImage.md)

