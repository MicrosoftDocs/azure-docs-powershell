---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmStorageAccount

## SYNOPSIS
Gets a storage account.

## SYNTAX

```
Get-AzureRmStorageAccount [[-ResourceGroupName] <String>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmStorageAccount** cmdlet gets a specified storage account or all storage accounts within a resource group or the subscription.

## EXAMPLES

### Example 1: Get a specified storage account
```
PS C:\> Get-AzureRmStorageAccount -ResourceGroupName "rg1" -Name "mystorageaccount"
```

This command gets the storage account named "mystorageaccount" in the "rg1" resource group.

### Example 2: Get all storage accounts in a resource group
```
PS C:\> Get-AzureRmStorageAccount -ResourceGroupName "rg1"
```

This command gets all storage accounts in the "rg1" resource group.

### Example 3: Get all storage accounts in the subscription
```
PS C:\> Get-AzureRmStorageAccount
```

This command gets all storage accounts in the subscription.

## PARAMETERS

### -Name
Specifies the name of the storage account to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageAccountName, AccountName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the storage account to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount

## NOTES

## RELATED LINKS

[New-AzureRmStorageAccount](./New-AzureRmStorageAccount.md)

[Remove-AzureRmStorageAccount](./Remove-AzureRmStorageAccount.md)

[Set-AzureRmStorageAccount](./Set-AzureRmStorageAccount.md)
