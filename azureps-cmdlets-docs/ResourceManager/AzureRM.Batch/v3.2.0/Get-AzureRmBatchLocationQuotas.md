---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
ms.assetid: A39A415A-B403-48D3-AF80-CF7CFE382577
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureRmBatchLocationQuotas.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureRmBatchLocationQuotas.md
gitcommit: https://github.com/Azure/azure-powershell/blob/8810c0614b76be8d014616888a4ae7733a452af9
---

# Get-AzureRmBatchLocationQuotas

## SYNOPSIS
Gets the Batch service quotas for your subscription at the given location.

## SYNTAX

```
Get-AzureRmBatchLocationQuotas [-Location] <String> [<CommonParameters>]
```

## DESCRIPTION
Gets the Batch service quotas for the specified subscription at the given location.

## EXAMPLES

### Example 1: Get the Batch service quotas for the subscription in the West US region
```
PS C:\>Get-AzureRmBatchLocationQuotas -Location "westus"
          AccountQuota Location
          ------------ --------
          1            westus
```

This command gets the quotas for the current subscription in the West US region.
The return value indicates that this subscription can create only one Batch account in that region.

## PARAMETERS

### -Location
Specifies the region for which this cmdlet checks the quotas.
For more information, see Azure Regions (https://azure.microsoft.com/regions).

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

### Microsoft.Azure.Commands.Batch.Models.PSBatchLocationQuotas

## NOTES

## RELATED LINKS

