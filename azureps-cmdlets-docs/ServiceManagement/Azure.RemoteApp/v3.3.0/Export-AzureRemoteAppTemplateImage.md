---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: D35C580F-437A-40F9-B6BA-412A1176292A
online version: 
schema: 2.0.0
---

# Export-AzureRemoteAppTemplateImage

## SYNOPSIS
Exports the template image of one Azure RemoteApp collection to the specified Azure storage account.

## SYNTAX

```
Export-AzureRemoteAppTemplateImage [-CollectionName] <String> [-DestinationStorageAccountName] <String>
 [-DestinationStorageAccountKey] <String> [-DestinationStorageAccountContainerName] <String>
 [-OverwriteExistingTemplateImage] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-AzureRemoteAppTemplateImage** cmdlet exports the template image of one Azure RemoteApp collection to the specified Azure storage account.

## EXAMPLES

### Example 1: Export a template image to the Azure storage account
```
PS C:\> Export-AzureRemoteAppTemplateImage -CollectionName "Contoso" -DestinationStorageAccountName "AccountName" -DestinationStorageAccountKey "AccountKey" -DestinationStorageAccountContainerName "ContainerName" -OverwriteExistingTemplateImage
```

This command exports the template image of the collection named Contoso to a container named ContainerName in the specified Azure storage account with name AccountName and key AccountKey.

## PARAMETERS

### -CollectionName
Specifies the name of the source Azure RemoteApp collection.

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

### -DestinationStorageAccountContainerName
Specifies the name of a container in the destination Azure storage account.

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

### -DestinationStorageAccountKey
Specifies the key of the destination Azure storage account.

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

### -DestinationStorageAccountName
Specifies the name of the destination Azure storage account.

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

### -OverwriteExistingTemplateImage
Indicates that the cmdlet overwrites the existing template image.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppTemplateImage](./Get-AzureRemoteAppTemplateImage.md)

[New-AzureRemoteAppTemplateImage](./New-AzureRemoteAppTemplateImage.md)

[Remove-AzureRemoteAppTemplateImage](./Remove-AzureRemoteAppTemplateImage.md)

[Rename-AzureRemoteAppTemplateImage](./Rename-AzureRemoteAppTemplateImage.md)


