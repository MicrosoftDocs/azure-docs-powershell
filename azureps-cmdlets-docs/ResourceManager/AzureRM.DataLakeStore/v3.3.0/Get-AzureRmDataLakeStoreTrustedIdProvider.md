---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
ms.assetid: D79080D5-2785-4C46-86FD-FDAA11117D17
online version: 
schema: 2.0.0
---

# Get-AzureRmDataLakeStoreTrustedIdProvider

## SYNOPSIS
Gets the specified trusted identity provider in the specified Data Lake Store.
If no provider is specified, then lists all providers for the account.

## SYNTAX

```
Get-AzureRmDataLakeStoreTrustedIdProvider [-Account] <String> [[-Name] <String>]
 [[-ResourceGroupName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmDataLakeStoreTrustedIdProvider** cmdlet gets the specified trusted identity provider in the specified Data Lake Store.
If no provider is specified, then lists all providers for the account.

## EXAMPLES

### Example 1: Get a specific trusted identity provider
```
PS C:\> Get-AzureRmDataLakeStoreTrustedIdProvider -AccountName "ContosoADL" -Name "MyProvider"
```

This command gets the provider named MyProvider from the account named ContosoADL.

### Example 2: List all providers in an account
```
PS C:\> Get-AzureRmDataLakeStoreTrustedIdProvider -AccountName "ContosoADL"
```

This command lists all providers under the account named ContosoADL.

## PARAMETERS

### -Account
Specifies the Data Lake Store account that this cmdlet gets the trusted identity provider from.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AccountName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the trusted identity provider that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of resource group under which this cmdlet gets the specified accounts trusted identity provider.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.DataLake.Store.Models.TrustedIdProvider

### System.Collections.Generic.IList`1[[Microsoft.Azure.Management.DataLake.Store.Models.TrustedIdProvider, Microsoft.Azure.Management.DataLake.Store, Version=0.12.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

## NOTES

## RELATED LINKS

[Add-AzureRmDataLakeStoreTrustedIdProvider](./Add-AzureRmDataLakeStoreTrustedIdProvider.md)

[Remove-AzureRmDataLakeStoreTrustedIdProvider](./Remove-AzureRmDataLakeStoreTrustedIdProvider.md)

[Set-AzureRmDataLakeStoreTrustedIdProvider](./Set-AzureRmDataLakeStoreTrustedIdProvider.md)
