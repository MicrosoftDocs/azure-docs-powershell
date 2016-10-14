---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version: .\Set-AzureRmStorageAccount.md
schema: 2.0.0
---

# Set-AzureRmCurrentStorageAccount

## SYNOPSIS
Modifies the current Storage account of the specified subscription.

## SYNTAX

### UsingResourceGroupAndNameParameterSet (Default)
```
Set-AzureRmCurrentStorageAccount -ResourceGroupName <String> -Name <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### UsingStorageContext
```
Set-AzureRmCurrentStorageAccount -Context <AzureStorageContext> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmCurrentStorageAccount** cmdlet modifies the current azure_2 Storage account of the specified azure_2 subscription in azure_2 PowerShell.
The current storage account is used as the default when you access Storage without specifying a Storage account name.

## EXAMPLES

### Example 1: Set the current Storage account
```
PS C:\>Set-AzureRmCurrentStorageAccount -ResourceGroupName "RG01" -AccountName "MyStorageAccount"
```

This command sets the default storage account for the specified subscription.

## PARAMETERS

### -ResourceGroupName
Specifies the resource group that contains the Storage account to modify.

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

### -Name
Specifies the name of the Storage account that this cmdlet modifies.

```yaml
Type: String
Parameter Sets: UsingResourceGroupAndNameParameterSet
Aliases: StorageAccountName, AccountName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Context
Specifies an **AzureStorageContext** object for the current Storage account.
To obtain a storage context object, use the New-AzureStorageContext cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureRmStorageAccount](.\Set-AzureRmStorageAccount.md)

