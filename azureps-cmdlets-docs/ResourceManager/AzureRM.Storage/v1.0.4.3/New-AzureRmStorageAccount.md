---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRmStorageAccount

## SYNOPSIS
Creates an Azure storage account.

## SYNTAX

```
New-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Type] <String> [-Location] <String>
 [[-Tags] <Hashtable[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmStorageAccount** cmdlet creates an Azure storage account.

## EXAMPLES

### Example 1: Create a storage account
```
New-AzureRmStorageAccount -ResourceGroupName "myresourcegroup" -Name "mystorageaccount" -Location "US West" -Type "Standard_GRS"
```

This command creates a storage account named "mystorageaccount" in the "myresourcegroup" resource group.

## PARAMETERS

### -Location
Specifies the location of the storage account to create.

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

### -Name
Specifies the name of the storage account to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageAccountName, AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group in which to create the storage account.

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

### -Tags
Specifies the tags to set on the storage account.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Specifies the SKU (stock-keeping unit) name of the storage account that this cmdlet creates. The SKU name indicates the account type.

The acceptable values for this parameter are:
- Standard_LRS -- locally redundant storage
- Standard_ZRS -- zone-redundant storage
- Standard_GRS -- geo-redundant storage
- Standard_RAGRS -- read access geo-redundant storage
- Premium_LRS -- premium locally redundant storage

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageAccountType, AccountType
Accepted values: Standard_LRS, Standard_ZRS, Standard_GRS, Standard_RAGRS, Premium_LRS

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
### System.Collections.Hashtable[]

## OUTPUTS

### Microsoft.Azure.Management.Storage.Models.StorageAccount

## NOTES

## RELATED LINKS

[Get-AzureRmStorageAccount](./Get-AzureRmStorageAccount.md)

[Remove-AzureRmStorageAccount](./Remove-AzureRmStorageAccount.md)

[Set-AzureRmStorageAccount](./Set-AzureRmStorageAccount.md)
