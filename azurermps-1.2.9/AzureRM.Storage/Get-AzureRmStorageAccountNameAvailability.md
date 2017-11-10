---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmStorageAccountNameAvailability

## SYNOPSIS
Checks whether a name is valid and available to use for an Azure storage account.

## SYNTAX

```
Get-AzureRmStorageAccountNameAvailability [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmStorageAccountNameAvailability** cmdlet checks whether a name is valid and available to use for an Azure storage account.

## EXAMPLES

### Example 1: Check the availability of a storage account name
```
PS C:\> Get-AzureRmStorageAccountNameAvailability -Name "ContosoStorage03"
```

This command checks the availability of the name "ContosoStorage03" for an Azure storage account.

## PARAMETERS

### -Name
Specifies the name that this cmdlet checks.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.Storage.Models.CheckNameAvailabilityResponse

## NOTES

## RELATED LINKS

[Azure Storage Manager Cmdlets](./AzureRM.Storage.md)
