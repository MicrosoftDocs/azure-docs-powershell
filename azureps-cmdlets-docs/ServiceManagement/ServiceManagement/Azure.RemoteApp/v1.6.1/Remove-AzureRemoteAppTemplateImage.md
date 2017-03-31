---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1E2BB4DB-6290-4CBD-B99F-F98D35216CC4
---

# Remove-AzureRemoteAppTemplateImage

## SYNOPSIS
Deletes an Azure RemoteApp template image.

## SYNTAX

```
Remove-AzureRemoteAppTemplateImage [-ImageName] <String> [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRemoteAppTemplateImage** cmdlet deletes an Azure RemoteApp template image.
A template image can deleted only if it is not linked to any Azure RemoteApp collection.

## EXAMPLES

### Example 1: Delete a template image
```
PS C:\>Remove-AzureRemoteAppTemplateImage -ImageName "ContosoApps"
```

This command deletes the template image named ContosoApps.

## PARAMETERS

### -ImageName
Specifies the name of the RemoteApp template image.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppTemplateImage](./Get-AzureRemoteAppTemplateImage.md)

[New-AzureRemoteAppTemplateImage](./New-AzureRemoteAppTemplateImage.md)

[Rename-AzureRemoteAppTemplateImage](./Rename-AzureRemoteAppTemplateImage.md)


