---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureAvailabilitySet.md
schema: 2.0.0
---

# Set-AzureVMSourceImage

## SYNOPSIS
Specifies the platform image for a virtual machine.

## SYNTAX

```
Set-AzureVMSourceImage [-VM] <PSVirtualMachine> [-PublisherName] <String> [-Offer] <String> [-Skus] <String>
 [-Version] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMSourceImage** cmdlet specifies the platform image to use for a virtual machine.

## EXAMPLES

### Example 1: Set values for an image
```
PS C:\>AvailabilitySet = Get-AzureAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzureVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> Set-AzureVMSourceImage -VM $VirtualMachine -PublisherName "MicrosoftWindowsServer" -Offer "WindowsServer" -Skus "2012-R2-Datacenter" -Version "latest"
```

The first command gets the availability set named AvailablitySet03 in the resource group named ResourceGroup11, and then stores that object in the $AvailabilitySet variable.

The second command creates a virtual machine object, and then stores it in the $VirtualMachine variable.
The command assigns a name and size to the virtual machine.
The virtual machine belongs to the availability set stored in $AvailabilitySet.

The final command sets values for publisher name, offer, SKU, and version.
The **Get-AzureVMImagePublisher**, **Get-AzureVMImageOffer**, **Get-AzureVMImageSku**, and **Get-AzureVMImage** cmdlets can discover these settings.

### Example 2: Use the image reference method to set values
```
PS C:\>$Publisher = (Get-AzureVMImagePublisher -Location "Central US") | select -ExpandProperty PublisherName | where { $_ -like '*Microsoft*Windows*Server' } 
PS C:\> $Offer = (Get-AzureVMImageOffer -Location "Central US" -PublisherName $Publisher[0]) | select -ExpandProperty Offer | where { $_ -like '*Windows*' } 
PS C:\> $Sku = (Get-AzureVMImageSku -Location "Central US" -PublisherName $Publisher[0] -Offer $Offer[0]) | select -ExpandProperty Skus
PS C:\> $Versions = (Get-AzureVMImage -Location "Central US" -Offer -Offer $Offer[0] -PublisherName $Publisher[0] -Skus $Sku[0]) | select -ExpandProperty Version
PS C:\> $VMImage = Get-AzureVMImageDetail -Location "Central US" -Offer -Offer $Offer[0] -PublisherName $Publisher[0] -Skus $Sku[0] -Version $Versions[0] 
PS C:\> $VirtualMachine07 = Set-AzureVMSourceImage -VM $VirtualMachine07 -ImageReference $VMImage
```

This example sets source image settings by using the image reference method.

## PARAMETERS

### -Offer
Specifies the type of VMImage offer.
To obtain an image offer, use the **Get-AzureVMImageOffer** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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
Specifies the name of a publisher of a VMImage.
To obtain a publisher, use the **Get-AzureVMImagePublisher** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Skus
Specfies a VMImage SKU.
To obtain SKUs, use the **Get-AzureVMImageSku** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies a version of a VMImage.
To use the latest version, specify a value of latest instead of a particular version.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the local virtual machine object to configure.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureAvailabilitySet](.\Get-AzureAvailabilitySet.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

[Get-AzureVMImagePublisher](.\Get-AzureVMImagePublisher.md)

[Get-AzureVMImageOffer](.\Get-AzureVMImageOffer.md)

[Get-AzureVMImageSku](.\Get-AzureVMImageSku.md)

[Get-AzureVMImage](.\Get-AzureVMImage.md)

