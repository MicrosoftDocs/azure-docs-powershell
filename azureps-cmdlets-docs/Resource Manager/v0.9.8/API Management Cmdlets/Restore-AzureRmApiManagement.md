---
external help file: RMAzure_Apimanagement.xml
online version: b3b67164-7adf-4fe3-87ab-51dcd46ed084
schema: 2.0.0
---

# Restore-AzureRmApiManagement
## SYNOPSIS
Restores an API Management Service from the specified azure_2 storage blob.

## SYNTAX

```
Restore-AzureRmApiManagement [-StorageContext] <AzureStorageContext> [-PassThru] -Name <String>
 -ResourceGroupName <String> -SourceBlobName <String> -SourceContainerName <String>
```

## DESCRIPTION
The **Restore-AzureRmApiManagement** cmdlet restores an API Management Service from the specified backup residing in an azure_2storage blob.

## EXAMPLES

### Example 1: Restore an API Management service
```
PS C:\>Restore-AzureRmApiManagement -ResourceGroupName "ContosoGroup" -Name "RestoredContosoApi" -StorageContext $StorageContext -SourceContainerName "ContosoBackups" -SourceBlobName "ContosoBackup.apimbackup"
```

This command restores an API Management service from azure_2 storage blob.

## PARAMETERS

### -Name
Specifies the name of the API Management instance that this cmdlet restores.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
passthru

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
Specifies the name of resource group under which API Management exists.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -SourceBlobName
Specifies the name of the azure_2 storage backup source blob.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -SourceContainerName
Specifies the name of the azure_2 storage backup source container.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -StorageContext
Specifies the storage connection context.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Backup-AzureRmApiManagement](b3b67164-7adf-4fe3-87ab-51dcd46ed084)

[Get-AzureRmApiManagement](e067ded3-a2e3-4d53-8628-0ebbafa62721)

[New-AzureRmApiManagement](6b5595ca-246e-4381-a37e-24dfae307109)

[Remove-AzureRmApiManagement](9a2c4617-9870-4d9c-92fa-2af03211d931)

