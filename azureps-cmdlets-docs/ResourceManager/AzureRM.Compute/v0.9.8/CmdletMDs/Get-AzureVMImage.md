---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVMImageOffer.md
schema: 2.0.0
---

# Get-AzureVMImage

## SYNOPSIS
Gets all the versions of a VMImage.

## SYNTAX

### ListVMImage
```
Get-AzureVMImage -Location <String> -PublisherName <String> -Offer <String> -Skus <String>
 [-FilterExpression <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### GetVMImageDetail
```
Get-AzureVMImage -Location <String> -PublisherName <String> -Offer <String> -Skus <String> -Version <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMImage** cmdlet gets all the versions of a **VMImage**.

## EXAMPLES

### Example 1: Get VMImage objects
```
PS C:\>Get-AzureVMImage -Location "Central US" -PublisherName "Canonical" -Offer "UbuntuServer" -Skus "15.04-DAILY"
```

This command gets all the versions of **VMImage** that match the specified values.

## PARAMETERS

### -FilterExpression
Specifies a filter expression.```yaml
Type: String
Parameter Sets: ListVMImage
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the location of a VMImage.```yaml
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
Specifies the type of VMImage offer. To obtain an image offer, use the Get-AzureVMImageOffer cmdlet.```yaml
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
Specifies the publisher of a VMImage. To obtain an image publisher, use the Get-AzureVMImagePublisher cmdlet.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Skus
Specifies a VMImage SKU. To obtain an SKU, use the Get-AzureVMImageSku cmdlet.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
@{Text=}```yaml
Type: String
Parameter Sets: GetVMImageDetail
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

[Get-AzureVMImageOffer](.\Get-AzureVMImageOffer.md)

[Get-AzureVMImagePublisher](.\Get-AzureVMImagePublisher.md)

[Get-AzureVMImageSku](.\Get-AzureVMImageSku.md)

[Save-AzureVMImage](.\Save-AzureVMImage.md)

