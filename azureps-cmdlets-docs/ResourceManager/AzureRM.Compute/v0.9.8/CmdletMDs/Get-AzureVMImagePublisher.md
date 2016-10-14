---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVMImage.md
schema: 2.0.0
---

# Get-AzureVMImagePublisher

## SYNOPSIS
Gets the VMImage publishers.

## SYNTAX

```
Get-AzureVMImagePublisher -Location <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVMImagePublisher** cmdlet gets the **VMImage** publishers.

## EXAMPLES

### Example 1: Get VMImage publishers for a region
```
PS C:\>Get-AzureVMImagePublisher -Location "Central US"
```

This command gets the publishers of **VMImage** instances for the Central US region within your profile.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVMImage](.\Get-AzureVMImage.md)

[Get-AzureVMImageOffer](.\Get-AzureVMImageOffer.md)

[Get-AzureVMImageSku](.\Get-AzureVMImageSku.md)

[Save-AzureVMImage](.\Save-AzureVMImage.md)

