---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmStorageAccount

## SYNOPSIS
Allows you to create a new Storage Account using the ARM deployment model

## SYNTAX

```
New-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-SkuName] <String>
 [-Location] <String> [[-Kind] <String>] [[-AccessTier] <String>] [[-CustomDomainName] <String>]
 [[-UseSubDomain] <Boolean>] [[-EnableEncryptionService] <EncryptionSupportServiceEnum>] [[-Tag] <Hashtable[]>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to create a new Storage Account using the ARM deployment model.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}



```
New-AzureRmStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -Location "US West" -SkuName "Standard_GRS" -Kind "Storage"
```

### --------------------------  Example 2  --------------------------
@{paragraph=PS C:\\\>}



```
New-AzureRmStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mycoolstorageaccount" -Location "US West" -SkuName "Standard_GRS" -EnableEncryptionService blob -Kind "BlobStorage" -AccessTier "hot"
```

## PARAMETERS

### -AccessTier
Access Tier for Blob Storage Accounts.
This is mandatory when Storage Account Kind is equal to BlobStorage.
Setting this will fail if Storage Account Kind is equal to Storage.
Valid values are:
• Hot
• Cool

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
The name of the custom domain.

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
This will enable Storage Service Encryption on the specified Azure Storage Service.
Only the Azure Blob Service is currently supported.

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
@{Text=}

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
@{Text=}

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
Kind of Storage Account.
Valid values are:
• Storage (General-purpose storage account which supports storing Blobs, Tables, Queues, Files and Disks)
• BlobStorage (Blob storage account which supports storing Blobs only)
Default is Storage.

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
Location of the Storage Account

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
Name of the Storage Account

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
Name of the Resource Group

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
SkuName of Storage Account.
Valid values are 
• Standard_LRS (Locally-redundant storage)
• Standard_ZRS (Zone-redundant storage)
• Standard_GRS (Geo-redundant storage)
• Standard_RAGRS (Read access geo-redundant storage)
• Premium_LRS (Premium Locally-redundant storage)

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
Tags to set on the storage account.

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
Indicates whether or not indirect CName validation is enabled.

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

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, storage, container, account

## RELATED LINKS

