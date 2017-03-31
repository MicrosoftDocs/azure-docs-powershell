---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: EBC63013-AE09-487D-A490-1BAB3B6AAC5C
---

# Export-AzureRemoteAppUserDisk

## SYNOPSIS
Exports all user disks from one Azure RemoteApp collection to the specified Azure storage account.

## SYNTAX

```
Export-AzureRemoteAppUserDisk [-CollectionName] <String> [-DestinationStorageAccountName] <String>
 [-DestinationStorageAccountKey] <String> [-DestinationStorageAccountContainerName] <String>
 [-OverwriteExistingUserDisk] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Export-AzureRemoteAppUserDisk** cmdlet exports all user disks from one Azure RemoteApp collection to the specified Azure storage account.

## EXAMPLES

### Example 1: Export all the user disks from a collection to the specified Azure storage account
```
PS C:\> Export-AzureRemoteAppUserDisk -CollectionName "Contoso" -DestinationStorageAccountName "AccountName" -DestinationStorageAccountKey "AccountKey" -DestinationStorageAccountContainerName "ContainerName" -OverwriteExistingUserDisk
```

This command exports all the user disks from the collection named Contoso to a container named ContainerName in the specified Azure storage account with name AccountName and key AccountKey.

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

### -DestinationStorageAccountKey
Specifies the Key of the destination Azure storage account.

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

### -OverwriteExistingUserDisk
Indicates that the cmdlet overwrites the existing user disk.

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

[Copy-AzureRemoteAppUserDisk](./Copy-AzureRemoteAppUserDisk.md)

[Remove-AzureRemoteAppUserDisk](./Remove-AzureRemoteAppUserDisk.md)


