---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureStorageAccount.md
schema: 2.0.0
---

# Get-AzureStorageKey

## SYNOPSIS
Returns the primary and secondary storage account keys for an azure_2 storage account.

## SYNTAX

```
Get-AzureStorageKey [-StorageAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorageKey** cmdlet returns an object with the azure_2 Storage account name, the primary account key, and the secondary account key of the specified azure_2 storage account as properties.

## EXAMPLES

### Example 1: Get an object that contains primary and secondary storage keys
```
PS C:\>Get-AzureStorageKey -StorageAccountName "ContosoStore01"
```

This command gets an object with the primary and secondary storage keys for the ContosoStore01 storage account.

### Example 2: Get the primary storage account key and store it in a variable
```
PS C:\>$ContosoStoreKey = (Get-AzureStorageKey -StorageAccountName "ContosoStore01").Primary
```

This command puts the primary storage account key for the ContosoStore01 storage account in the $ContosoStoreKey variable.

## PARAMETERS

### -StorageAccountName
Specifies the storage account name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
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
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* To get help with Node.js, use the `help node-dev` command. For help with PHP extensions, use the `help php-dev` command.

## RELATED LINKS

[Get-AzureStorageAccount](.\Get-AzureStorageAccount.md)

[New-AzureStorageAccount](.\New-AzureStorageAccount.md)

[New-AzureStorageKey](.\New-AzureStorageKey.md)

[Remove-AzureStorageAccount](.\Remove-AzureStorageAccount.md)

[Set-AzureStorageAccount](.\Set-AzureStorageAccount.md)

