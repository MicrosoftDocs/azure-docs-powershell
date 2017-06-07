---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRmStorageAccount

## SYNOPSIS
Updates the properties of a storage account.

## SYNTAX

```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [[-SkuName] <String>]
 [[-AccessTier] <String>] [[-CustomDomainName] <String>] [[-UseSubDomain] <Boolean>]
 [[-EnableEncryptionService] <EncryptionSupportServiceEnum>]
 [[-DisableEncryptionService] <EncryptionSupportServiceEnum>] [[-Tag] <Hashtable[]>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmStorageAccount** cmdlet updates the properties of a storage account.

## EXAMPLES

### Example 1: Set the storage account type
```
PS C:\> Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -Name "MyStorageAccount" - SkuName "Standard_RAGRS"
```

This command sets the storage account type to "Standard_RAGRS" for the storage account named "MyStorageAccount".

### Example 2: Set a custom domain for a storage account
```
PS C:\> Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -Name "MyStorageAccount" -CustomDomainName "www.contoso.com" -UseSubDomain $True
```

This command sets a custom domain "www.contoso.com" for the storage account named "MyStorageAccount".

### Example 3: Enable encryption on Blob storage and File storage
```
PS C:\> Set-AzureRmStorageAccount -ResourceGroupName "MyResourceGroup" -Name "MyStorageAccount" -EnableEncryptionService "Blob,File"
```

This command enables storage encryption on Blob storage and File storage for the storage account named "MyStorageAccount".

## PARAMETERS

### -AccessTier
Specifies the access tier of the storage account.
Changing the access tier may result in additional charges.
For more information, see [Azure Blob Storage: Hot and cool storage tiers](http://go.microsoft.com/fwlink/?LinkId=786482).

If you specified a value of "BlobStorage" for the *Kind* parameter of the **New-AzureRmStorageAccount** cmdlet when you created the storage account, you must specify a value for the *AccessTier* parameter in the **Set-AzureRmStorageAccount** cmdlet.
If you specified a value of "Storage" for the *Kind*  parameter of the **New-AzureRmStorageAccount** cmdlet when you created the storage account, do not include the *AccessTier* parameter in the **Set-AzureRmStorageAccount** cmdlet.

The valid values for this parameter are:

- Hot
- Cool

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomDomainName
Specifies the name of the custom domain of the storage account.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableEncryptionService
Specifies the Azure Storage on which to disable encryption.
Encryption is supported only on the Azure Blob storage.

```yaml
Type: EncryptionSupportServiceEnum
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableEncryptionService
Specifies the Azure Storage on which to enable encryption.
Encryption is supported only on the Azure Blob storage.

```yaml
Type: EncryptionSupportServiceEnum
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies a variable that is used for storing an informational message.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -SkuName
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
Parameter Sets: (All)
Aliases: StorageAccountType, AccountType, Type

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies the tags to set on the storage account.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSubDomain
Indicates whether to enable indirect validation of the *CName* (canonical name).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-AzureRmStorageAccount](./Get-AzureRmStorageAccount.md)

[New-AzureRmStorageAccount](./New-AzureRmStorageAccount.md)

[Remove-AzureRmStorageAccount](./Remove-AzureRmStorageAccount.md)
