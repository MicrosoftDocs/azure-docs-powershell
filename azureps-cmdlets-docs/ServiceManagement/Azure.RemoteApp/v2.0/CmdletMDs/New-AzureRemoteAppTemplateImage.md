---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppTemplateImage.md
schema: 2.0.0
---

# New-AzureRemoteAppTemplateImage

## SYNOPSIS
Uploads or imports an Azure RemoteApp template image.

## SYNTAX

### UploadLocalVhd (Default)
```
New-AzureRemoteAppTemplateImage [-ImageName] <String> [-Location] <String> [-Path] <String> [-Resume]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### AzureVmUpload
```
New-AzureRemoteAppTemplateImage [-ImageName] <String> [-Location] <String> -AzureVmImageName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRemoteAppTemplateImage** cmdlet uploads or imports an Azure RemoteApp template image.

## EXAMPLES

### Example 1: Upload a VHD file to create a template image
```
PS C:\>New-AzureRemoteAppTemplateImage -ImageName "ContosoApps" -Location "North Europe" -Path "C:\RemoteAppImages\ContosoApps.vhd"
```

This command uploads C:\RemoteAppImages\ContosoApps.vhd to create a template image named ContosoApps in the North Europe data center.

## PARAMETERS

### -ImageName
Specifies the name of an Azure RemoteApp template image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
Specifies the Azure region of the template image.

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

### -Path
Specifies the file path of the template image.

```yaml
Type: String
Parameter Sets: UploadLocalVhd
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Resume
Indicates that this cmdlet resumes if the upload of a template image is interrupted.

```yaml
Type: SwitchParameter
Parameter Sets: UploadLocalVhd
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureVmImageName
Specifies the name of an Azure virtual machine to use as a template image.

```yaml
Type: String
Parameter Sets: AzureVmUpload
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
Type: AzureSMProfile
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

[Get-AzureRemoteAppTemplateImage](.\Get-AzureRemoteAppTemplateImage.md)

[Remove-AzureRemoteAppTemplateImage](.\Remove-AzureRemoteAppTemplateImage.md)

[Rename-AzureRemoteAppTemplateImage](.\Rename-AzureRemoteAppTemplateImage.md)

