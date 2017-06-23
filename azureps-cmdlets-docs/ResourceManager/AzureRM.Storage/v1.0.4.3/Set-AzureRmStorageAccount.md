---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRmStorageAccount

## SYNOPSIS
Updates the properties of a storage account.

## SYNTAX

### UpdateAccountType (Default)
```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Type] <String> [<CommonParameters>]
```

### UpdateCustomDomain
```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-CustomDomainName] <String>
 [[-UseSubDomain] <Boolean>] [<CommonParameters>]
```

### UpdateTags
```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Tags] <Hashtable[]>
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmStorageAccount** cmdlet updates the properties of a storage account.

## EXAMPLES

### Example 1: Set the storage account type
```
Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -Name "MyStorageAccount" -Type "Standard_RAGRS"
```

This command sets the storage account type to "Standard_RAGRS" for the storage account named "MyStorageAccount".

### Example 2: Set a custom domain for a storage account
```
Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -Name "MyStorageAccount" -CustomDomainName "www.contoso.com" -UseSubDomain $True
```

This command sets a custom domain "www.contoso.com" for the storage account named "MyStorageAccount".

## PARAMETERS

### -CustomDomainName
Specifies the name of the custom domain of the storage account.

```yaml
Type: String
Parameter Sets: UpdateCustomDomain
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage account to update.

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
Specifies the name of the resource group that contains the storage account to update.

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
Parameter Sets: UpdateTags
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Specifies the SKU (stock-keeping unit) name of the storage account. The SKU name indicates the account type.

The acceptable values for this parameter are:
- Standard_LRS -- locally redundant storage
- Standard_ZRS -- zone-redundant storage
- Standard_GRS -- geo-redundant storage
- Standard_RAGRS -- read access geo-redundant storage
- Premium_LRS -- premium locally redundant storage

A storage account that is either "Standard_ZRS" or "Premium_LRS" cannot be changed to any other account type; likewise, other account types cannot be changed to either "Standard_ZRS" or "Premium_LRS".

```yaml
Type: String
Parameter Sets: UpdateAccountType
Aliases:
Accepted values: Standard_LRS, Standard_ZRS, Standard_GRS, Standard_RAGRS, Premium_LRS

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSubDomain
Indicates whether to enable indirect validation of the *CName* (canonical name).

```yaml
Type: Boolean
Parameter Sets: UpdateCustomDomain
Aliases:

Required: False
Position: 3
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

[New-AzureRmStorageAccount](./New-AzureRmStorageAccount.md)

[Remove-AzureRmStorageAccount](./Remove-AzureRmStorageAccount.md)
