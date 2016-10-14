---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureVMImage.md
schema: 2.0.0
---

# Remove-AzureVMImage

## SYNOPSIS
Removes an operating system image from the image repository.

## SYNTAX

```
Remove-AzureVMImage [-ImageName] <String> [-DeleteVHD] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureVMImage** cmdlet removes an operating system image from the image repository.
By default, this cmdlet does not delete the associated physical image blob from the storage account.
To delete the associated virtual hard drive (VHD), use the **DeleteVHD** parameter.

## EXAMPLES

### Example 1: Remove an image from the image repository
```
PS C:\>Remove-AzureVMImage -ImageName "Image001"
```

This command removes the image named Image001 from the image repository.

### Example 2: Remove an image from the image repository and also the VHD
```
PS C:\>Remove-AzureVMImage -ImageName " Image001" -DeleteVHD
```

This command removes the image named Image001 from the image repository and also deletes the physical VHD image from the storage account.

### Example 3: Set a subscription context and then remove all the images
```
PS C:\>$SubsId = &amp;lt;MySubscriptionID&amp;gt;
PS C:\> $Cert = Get-AzureCertificate cert:\LocalMachine\MY\&amp;lt;CertificateThumbprint&amp;gt;
PS C:\>Get-AzureVMImage `
| Where-Object {$_.Label -match "Beta" }`
| Foreach-Object {Remove-AzureVMImage -ImageName $_.name }
```

This command sets the subscription context and then removes all the images from the image repository whose Label includes the name Beta.

## PARAMETERS

### -ImageName
Specifies the operating system or virtual machine image to remove from the image repository.

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

### -DeleteVHD
Indicates that this cmdlet deletes the physical VHD image blob from the storage account.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Add-AzureVMImage](.\Add-AzureVMImage.md)

[Get-AzureVMImage](.\Get-AzureVMImage.md)

[Save-AzureVMImage](.\Save-AzureVMImage.md)

[Update-AzureVMImage](.\Update-AzureVMImage.md)

