---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Backup-AzureRmApiManagement

## SYNOPSIS
Backs up an instance of the Azure API Management service.

## SYNTAX

```
Backup-AzureRmApiManagement -ResourceGroupName <String> -Name <String> -StorageContext <AzureStorageContext>
 -TargetContainerName <String> [-TargetBlobName <String>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Backup-AzureRmApiManagement** cmdlet backs up an instance of the Azure API Management service.
This cmdlet stores the backup as an Azure Storage blob.

## EXAMPLES

### Example 1: Back up an instance of the Azure API Management service
```
PS C:\>Backup-AzureRmApiManagement -ResourceGroupName "ContosoGroup02" -Name "ContosoApi" -StorageContext $StorageContext -TargetContainerName "ContosoBackups" -TargetBlobName "ContosoBackup.apimbackup"
```

This command backs up the API Management service deployment named "ContosoApi" and stores the backup in a Storage blob named "ContosoBackup.apimbackup".

## PARAMETERS

### -Name
Specifies the name of the API Management deployment to be backed up.

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
Specifies whether to return an object representing the API Management service deployment that is backed up.
By default, this cmdlet does not generate any output.

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
Specifies the name of the of resource group under which the API Management deployment exists.

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
Specifies the storage connection context.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetBlobName
Specifies the name of the blob in which to store the backup.
If the blob does not exist, this cmdlet creates it.
This cmdlet generates a default name based on the following pattern:

{Name}-{yyyy-MM-dd-HH-mm}.apimbackup

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetContainerName
Specifies the name of the container of the blob.
If the container does not exist, this cmdlet creates it.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.Common.Storage.AzureStorageContext

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Get-AzureRmApiManagement](./Get-AzureRmApiManagement.md)

[New-AzureRmApiManagement](./New-AzureRmApiManagement.md)

[Remove-AzureRmApiManagement](./Remove-AzureRmApiManagement.md)

[Restore-AzureRmApiManagement](./Restore-AzureRmApiManagement.md)
