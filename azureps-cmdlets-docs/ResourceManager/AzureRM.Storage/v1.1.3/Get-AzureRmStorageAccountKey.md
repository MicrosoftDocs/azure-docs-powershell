---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmStorageAccountKey

## SYNOPSIS
Gets the access keys for an Azure storage account.

## SYNTAX

```
Get-AzureRmStorageAccountKey [-ResourceGroupName] <String> [-Name] <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmStorageAccountKey** cmdlet gets the access keys for an Azure storage account.

## EXAMPLES

### Example 1: Get all access keys for a storage account
```
PS C:\> Get-AzureRmStorageAccountKey -ResourceGroupName "RG01" -Name "MyStorageAccount"
```

This command gets all access keys for the storage account named "MyStorageAccount" in the "RG01" resource group.

### Example 2: Get a specific access key for a storage account
```
PS C:\> (Get-AzureRmStorageAccountKey -ResourceGroupName "RG01" -Name "MyStorageAccount").Key1
```

This command gets a specific access key for the storage account named "MyStorageAccount" in the "RG01" resource group.

## PARAMETERS

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
Specifies the name of the storage account for which this cmdlet gets keys.

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
Specifies the name of the resource group that contains the storage account.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-AzureRmStorageAccountKey](./New-AzureRmStorageAccountKey.md)
