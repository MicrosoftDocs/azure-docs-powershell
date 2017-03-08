---
external help file: Microsoft.Azure.Commands.DataLakeStore.dll-Help.xml
ms.assetid: BDEF8BAA-0C64-465D-9ED4-6FEFC1E850CC
online version: 
schema: 2.0.0
---

# Set-AzureRmDataLakeStoreTrustedIdProvider

## SYNOPSIS
Modifies the specified trusted identity provider in the specified Data Lake Store.

## SYNTAX

```
Set-AzureRmDataLakeStoreTrustedIdProvider [-Account] <String> [-Name] <String> [-ProviderEndpoint] <String>
 [[-ResourceGroupName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmDataLakeStoreTrustedIdProvider** cmdlet modifies the specified trusted identity provider in the specified Data Lake Store.

## EXAMPLES

### Example 1: Update a Trusted Identity Provider Endpoint
```
PS C:\> Set-AzureRmDataLakeStoreTrustedIdProvider -AccountName "ContosoADL" -Name MyProvider -ProviderEndpoint "https://sts.windows.net/6b04908c-b91f-40ce-8024-7ee8a4fd6150"
```

This command updates the provider endpoint for the firewall rule named MyProvider in the account named ContosoADL to "https://sts.windows.net/6b04908c-b91f-40ce-8024-7ee8a4fd6150".

## PARAMETERS

### -Account
Specifies the Data Lake Store account that this cmdlet adds the trusted identity provider.

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
Specifies the name of the trusted identity provider.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProviderEndpoint
Specifies the valid trusted provider endpoint in the format: https://sts.windows.net/\<provider identity\>.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the account to update the trusted identity provider for.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### Microsoft.Azure.Management.DataLake.Store.Models.TrustedIdProvider

## NOTES

## RELATED LINKS

[Add-AzureRmDataLakeStoreTrustedIdProvider](./Add-AzureRmDataLakeStoreTrustedIdProvider.md)

[Get-AzureRmDataLakeStoreTrustedIdProvider](./Get-AzureRmDataLakeStoreTrustedIdProvider.md)

[Remove-AzureRmDataLakeStoreTrustedIdProvider](./Remove-AzureRmDataLakeStoreTrustedIdProvider.md)
