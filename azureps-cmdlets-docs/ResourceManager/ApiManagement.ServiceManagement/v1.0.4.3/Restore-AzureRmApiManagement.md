---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Restore-AzureRmApiManagement

## SYNOPSIS
Restores an API Management service.

## SYNTAX

```
Restore-AzureRmApiManagement -ResourceGroupName <String> -Name <String> [-StorageContext] <AzureStorageContext>
 -SourceContainerName <String> -SourceBlobName <String> [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-AzureRmApiManagement** cmdlet restores an API Management service from the specified backup residing in Azure Blob storage.

## EXAMPLES

### Example 1: Restore an API Management service
```
PS C:\> Restore-AzureRmApiManagement -ResourceGroupName "ContosoGroup" -Name "RestoredContosoApi" -StorageContext $StorageContext -SourceContainerName "ContosoBackups" -SourceBlobName "ContosoBackup.apimbackup"
```

This command restores the API Management service named "RestoredContosoApi" from the backup named "ContosoBackup.apimbackup".

## PARAMETERS

### -Name
Specifies the name of the API Management instance that will be restored from the backup.

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

### -PassThru
Specifies whether to return an object representing the restored item.

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

### -ResourceGroupName
Specifies the name of resource group under which the API Management service exists.

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

### -SourceBlobName
Specifies the name of the backup residing in Azure Blob storage.

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

### -SourceContainerName
Specifies the name of the container of the backup.

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

### -StorageContext
Specifies the context of the storage connection.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Backup-AzureRmApiManagement](./Backup-AzureRmApiManagement.md)

[Get-AzureRmApiManagement](./Get-AzureRmApiManagement.md)

[New-AzureRmApiManagement](./New-AzureRmApiManagement.md)

[Remove-AzureRmApiManagement](./Remove-AzureRmApiManagement.md)
