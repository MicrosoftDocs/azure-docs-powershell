---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
online version: .\Get-AzureRmSiteRecoveryStorageClassificationMapping.md
schema: 2.0.0
---

# New-AzureRmSiteRecoveryStorageClassificationMapping

## SYNOPSIS
Creates a storage classification mapping in Site Recovery.

## SYNTAX

```
New-AzureRmSiteRecoveryStorageClassificationMapping -PrimaryStorageClassification <ASRStorageClassification>
 -RecoveryStorageClassification <ASRStorageClassification> [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmSiteRecoveryStorageClassificationMapping** cmdlet creates a storage classification mapping in azure_2 Site Recovery.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -PrimaryStorageClassification
Specifies the primary storage classification mapping.

```yaml
Type: ASRStorageClassification
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryStorageClassification
Specifies a recovery storage classification mapping.

```yaml
Type: ASRStorageClassification
Parameter Sets: (All)
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

## NOTES

## RELATED LINKS

[Get-AzureRmSiteRecoveryStorageClassificationMapping](.\Get-AzureRmSiteRecoveryStorageClassificationMapping.md)

[Remove-AzureRmSiteRecoveryStorageClassificationMapping](.\Remove-AzureRmSiteRecoveryStorageClassificationMapping.md)

