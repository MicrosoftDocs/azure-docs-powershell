---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppTemplateImage.md
schema: 2.0.0
---

# Rename-AzureRemoteAppTemplateImage

## SYNOPSIS
Renames a RemoteApp template image.

## SYNTAX

```
Rename-AzureRemoteAppTemplateImage [-ImageName] <String> [-NewName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Rename-AzureRemoteAppTemplate** cmdlet renames an Azure RemoteApp template image.

## EXAMPLES

### Example 1: Rename a RemoteApp template image
```
PS C:\>Rename-AzureRemoteAppTemplateImage -ImageName "ContosoApps" -NewName "ContosoFinanceApps"
```

This command renames the RemoteApp template image named ContosoApps to ContosoFinanceApps.

## PARAMETERS

### -ImageName
Specifies the name of a RemoteApp template image to rename.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewName
Specifies a new name for a RemoteApp template image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

[Get-AzureRemoteAppTemplateImage](.\Get-AzureRemoteAppTemplateImage.md)

[New-AzureRemoteAppTemplateImage](.\New-AzureRemoteAppTemplateImage.md)

[Remove-AzureRemoteAppTemplateImage](.\Remove-AzureRemoteAppTemplateImage.md)

