---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppTemplateImage.md
schema: 2.0.0
---

# Remove-AzureRemoteAppTemplateImage

## SYNOPSIS
Deletes a RemoteApp template image.

## SYNTAX

```
Remove-AzureRemoteAppTemplateImage [-ImageName] <String> [-Profile <AzureProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The cmdlet deletes an Azure RemoteApp template image.
A template image can deleted only if it is not linked to any RemoteApp collection.

## EXAMPLES

### Example 1: Delete a template image
```
PS C:\>Remove-AzureRemoteAppTemplateImage -ImageName "ContosoApps"
```

This command deletes the template image named ContosoApps.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

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

### -ImageName
Specifies the name of the RemoteApp template image.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppTemplateImage](.\Get-AzureRemoteAppTemplateImage.md)

[New-AzureRemoteAppTemplateImage](.\New-AzureRemoteAppTemplateImage.md)

[Rename-AzureRemoteAppTemplateImage](.\Rename-AzureRemoteAppTemplateImage.md)

