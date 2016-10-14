---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureVMImage.md
schema: 2.0.0
---

# Update-AzureVMImage

## SYNOPSIS
Updates the label of an operating system image in the image repository.

## SYNTAX

```
Update-AzureVMImage [-ImageName] <String> [-Label] <String> [[-Eula] <String>] [[-Description] <String>]
 [[-ImageFamily] <String>] [[-PublishedDate] <DateTime>] [[-PrivacyUri] <Uri>] [[-RecommendedVMSize] <String>]
 [[-DiskConfig] <VirtualMachineImageDiskConfigSet>] [[-Language] <String>] [-IconName <String>]
 [-SmallIconName <String>] [-DontShowInGui] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzureVMImage** cmdlet updates the label on an operating system image in the image repository.
It returns an image object with information about the updated image.

## EXAMPLES

### Example 1: Update an image by changing the image label
```
PS C:\>Update-AzureVMImage -ImageName "Windows-Server-2008-SP2" -Label "DoNotUse"
```

This command updates the image named Windows-Server-2008-SP2 by changing the image label to DoNotUse.

### Example 2: Get all operating systems by label and then update the label
```
PS C:\>Get-AzureVMImage | Where-Object {$_.Label -eq "DoNotUse" } | Update-AzureVMImage -Label "Updated"
```

This command gets all the operating system images labeled DoNotUse and changes the label to Updated.

## PARAMETERS

### -ImageName
Specifies the name of the image to update in the image repository.

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

### -Label
Specifies the new label of the image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Eula
Specifies the End User License Agreement.
We recommend that the value is a URL.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies the description of the operating system image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImageFamily
Specifies a value that can be used to group operating system or virtual machine images.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishedDate
Specifies the date when the operating system image was added to the image repository.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivacyUri
Specifies the URI that points to a document that contains the privacy policy related to the operating system image.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecommendedVMSize
Specifies the size of the virtual machine.

The acceptable values for this parameter are:

- Medium
- Large
- ExtraLarge
- A5
- A6
- A7

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskConfig
Specifies the operating system disk and data disk configuration for the virtual machine image created by using the New-AzureVMImageDiskConfigSet, Set-AzureVMImageOSDiskConfig, and Set-AzureVMImageDataDiskConfig cmdlets.

```yaml
Type: VirtualMachineImageDiskConfigSet
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Language
Specifies the language for the operating system in the virtual machine or operating system image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DontShowInGui
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IconName
Specifies the standard icon name for the operating system or virtual machine image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IconUri

Required: False
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

### -SmallIconName
Specifies the small icon name for the operating system or virtual machine image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SmallIconUri

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### OSImageContext

## NOTES

## RELATED LINKS

[Add-AzureVMImage](.\Add-AzureVMImage.md)

[Get-AzureVMImage](.\Get-AzureVMImage.md)

[Remove-AzureVMImage](.\Remove-AzureVMImage.md)

[Save-AzureVMImage](.\Save-AzureVMImage.md)

[New-AzureVMImageDiskConfigSet](.\New-AzureVMImageDiskConfigSet.md)

[Set-AzureVMImageOSDiskConfig](.\Set-AzureVMImageOSDiskConfig.md)

[Set-AzureVMImageDataDiskConfig](.\Set-AzureVMImageDataDiskConfig.md)

