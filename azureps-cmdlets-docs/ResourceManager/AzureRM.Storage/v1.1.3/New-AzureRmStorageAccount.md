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
New-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-SkuName] <String>
 [-Location] <String> [[-Kind] <String>] [[-AccessTier] <String>] [[-CustomDomainName] <String>]
 [[-UseSubDomain] <Boolean>] [[-EnableEncryptionService] <EncryptionSupportServiceEnum>] [[-Tag] <Hashtable[]>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmStorageAccount** cmdlet creates an Azure storage account.

## EXAMPLES

### Example 1: Create a storage account
```
PS C:\> New-AzureRmStorageAccount -ResourceGroupName "myresourcegroup" -Name "mystorageaccount" -Location "US West" -SkuName "Standard_GRS" -Kind "Storage"
```

This command creates a storage account named "mystorageaccount" in the "myresourcegroup" resource group.

### Example 2: Create a Blob storage account with encryption enabled
```
PS C:\> New-AzureRmStorageAccount -ResourceGroupName "myresourcegroup" -Name "mycoolstorageaccount" -Location "US West" -SkuName "Standard_GRS" -EnableEncryptionService blob -Kind "BlobStorage" -AccessTier "hot"
```

This command creates a Blob storage account named "mycoolstorageaccount" with encryption enabled.

## PARAMETERS

### -AccessTier
Specifies the access tier of the storage account that this cmdlet creates.
If you specify a value of "BlobStorage" for the *Kind* parameter, you must specify a value for the *AccessTier* parameter.
If you specify a value of "Storage" for the *Kind*  parameter, do not include the *AccessTier* parameter.

The valid values for this parameter are:

- Hot
- Cool

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

### -CustomDomainName
Specifies the name of the custom domain of the storage account.
The default value is "Storage".

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
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
Position: 8
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

### -Kind
Specifies the type of Azure Storage to be used by the storage account that this cmdlet creates.

The acceptable values for this parameter are:
- Storage -- General-purpose storage, which supports storing blobs, tables, queues, files, and disks
- BlobStorage -- Blob storage, which supports storing only blobs

The default value is "Storage".

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

### -Location
Specifies the location of the storage account to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 5
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

### -SkuName
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
Aliases: StorageAccountType, AccountType, Type

Required: True
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
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSubDomain
Indicates whether to enable indirect validation of the *CName* (canonical name).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
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

[Remove-AzureRmStorageAccount](./Remove-AzureRmStorageAccount.md)

[Set-AzureRmStorageAccount](./Set-AzureRmStorageAccount.md)
