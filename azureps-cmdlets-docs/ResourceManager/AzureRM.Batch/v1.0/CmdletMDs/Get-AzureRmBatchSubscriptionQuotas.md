---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureRmBatchAccountKeys.md
schema: 2.0.0
---

# Get-AzureRmBatchSubscriptionQuotas

## SYNOPSIS
Gets the quota for your subscription in the Batch service for a region.

## SYNTAX

```
Get-AzureRmBatchSubscriptionQuotas [-Location] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmBatchSubscriptionQuotas** cmdlet gets the quota of accounts for your subscription in the azure_2 Batch service for the specified region.

## EXAMPLES

### Example 1: Get the quota for the subscription in the West US region
```
PS C:\>Get-AzureRmBatchSubscriptionQuotas -Location "westus"
AccountQuota Location
------------ --------
1            westus
```

This command gets the quota for the current subscription in the West US region.
The return value indicates that this subscription can create only one account in that region.

## PARAMETERS

### -Location
Specifies the region for which this cmdlet checks the quota.
For more information, see Azure Regionshttps://azure.microsoft.com/en-us/regions (https://azure.microsoft.com/en-us/regions).

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

## OUTPUTS

### PSBatchSubscriptionQuotas

## NOTES

## RELATED LINKS

[Get-AzureRmBatchAccountKeys](.\Get-AzureRmBatchAccountKeys.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

