---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmStorageAccount

## SYNOPSIS
Update the Storage Account properties

## SYNTAX

```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [[-SkuName] <String>]
 [[-AccessTier] <String>] [[-CustomDomainName] <String>] [[-UseSubDomain] <Boolean>]
 [[-EnableEncryptionService] <EncryptionSupportServiceEnum>]
 [[-DisableEncryptionService] <EncryptionSupportServiceEnum>] [[-Tag] <Hashtable[]>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet allows you to update the Storage Account properties.

## EXAMPLES

### --------------------------  Set Storage SkuName  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> # Set account type
              Set-AzureRmStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" - SkuName "Standard_RAGRS"
```

### --------------------------  Set Custom Domain  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> #Set custom domain
          Set-AzureRmStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -CustomDomainName "www.domainname.com" -UseSubDomain $true
```

### --------------------------  Enable Storage Service Encryption and set Access Tier to cool  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> #Enable Storage Service Encryption and set Access Tier to cool
          Set-AzureRmStorageAccount -ResourceGroupName "myresourcegroup" -AccountName "mycoolstorageaccount" -EnableEncryptionService blob -AccessTier "cool"
```

## PARAMETERS

### -AccessTier
Access Tier for Blob Storage Accounts.
Changing the access tier may result in additional charges.
See (http://go.microsoft.com/fwlink/?LinkId=786482) to learn more.
Setting this will fail if Storage Account Kind is equal to Storage.
Valid values are:
• Hot
• Cool

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
The name of the custom domain.

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
This will disable Storage Service Encryption on the specified Azure Storage Service.
Only the Azure Blob Service is currently supported.

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
This will enable Storage Service Encryption on the specified Azure Storage Service.
Only the Azure Blob Service is currently supported.

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
Specifies the account SkuName of the storage account.
The available options are:
• Standard_LRS (Locally-redundant storage)
• Standard_ZRS (Zone-redundant storage)
• Standard_GRS (Geo-redundant storage)
• Standard_RAGRS (Read access geo-redundant storage)
• Premium_LRS (Premium Locally-redundant storage)
          
Note that Standard_ZRS, Premium_LRS accounts cannot be changed to other account types, and other account types cannot be changed to Standard_ZRS, Premium_LRS.

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
Tags to set on the storage account.

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
Indicates whether or not indirect CName validation is enabled.

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

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, storage, container, account

## RELATED LINKS

