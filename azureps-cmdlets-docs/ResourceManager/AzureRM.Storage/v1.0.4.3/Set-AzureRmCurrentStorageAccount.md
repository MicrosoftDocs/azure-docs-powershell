---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRmCurrentStorageAccount

## SYNOPSIS
Sets the specified storage account as the current storage account.

## SYNTAX

### UsingResourceGroupAndNameParameterSet (Default)
```
Set-AzureRmCurrentStorageAccount -ResourceGroupName <String> -StorageAccountName <String> [<CommonParameters>]
```

### UsingStorageContext
```
Set-AzureRmCurrentStorageAccount -Context <AzureStorageContext> [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmCurrentStorageAccount** cmdlet sets the specified storage account as the current storage account.
The current storage account is the storage account that is used by default when you access Azure Storage without specifying a storage account name.

## EXAMPLES

### Example 1: Set the current storage account
```
Set-AzureRmCurrentStorageAccount -ResourceGroupName "RG01" -StorageAccountName "MyStorageAccount"
```

This command sets the storage account named "MyStorageAccount" in the "RG01" resource group as the default storage account.

## PARAMETERS

### -Context
Specifies an **AzureStorageContext** object for the current storage account.
The **AzureStorageContext** object includes authentication information and environment information.
Use the **New-AzureStorageContext** cmdlet to create this object.

```yaml
Type: AzureStorageContext
Parameter Sets: UsingStorageContext
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the storage account.

```yaml
Type: String
Parameter Sets: UsingResourceGroupAndNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the name of the storage account to be used as the current (default) storage account.

```yaml
Type: String
Parameter Sets: UsingResourceGroupAndNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsAzure.Commands.Common.Storage.AzureStorageContext
### System.String

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[New-AzureStorageContext](https://docs.microsoft.com/powershell/module/azure.storage/new-azurestoragecontext)

[Set-AzureRmStorageAccount](./Set-AzureRmStorageAccount.md)
