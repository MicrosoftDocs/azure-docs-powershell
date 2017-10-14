---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
ms.assetid: D19488C1-9E87-4F1A-94E3-8AFDE6AFC982
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoveryStorageClassificationMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoveryStorageClassificationMapping.md
gitcommit: https://github.com/Azure/azure-powershell/blob/1fa63f743120d7a7cd6cbb28ee43cd0f4c654af9
---

# Get-AzureRmSiteRecoveryStorageClassificationMapping

## SYNOPSIS
Gets a storage classification mapping in Site Recovery.

## SYNTAX

### Default (Default)
```
Get-AzureRmSiteRecoveryStorageClassificationMapping [<CommonParameters>]
```

### ByName
```
Get-AzureRmSiteRecoveryStorageClassificationMapping -Name <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSiteRecoveryStorageClassificationMapping** cmdlet gets a storage classification mapping in Azure Site Recovery.

## EXAMPLES

## PARAMETERS

### -Name
Specifies the name of the storage classification mapping that this cmdlet gets.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Collections.Generic.IEnumerable`1[Microsoft.Azure.Commands.SiteRecovery.ASRStorageClassificationMapping]

## NOTES

## RELATED LINKS

[New-AzureRmSiteRecoveryStorageClassificationMapping](./New-AzureRmSiteRecoveryStorageClassificationMapping.md)

[Remove-AzureRmSiteRecoveryStorageClassificationMapping](./Remove-AzureRmSiteRecoveryStorageClassificationMapping.md)
