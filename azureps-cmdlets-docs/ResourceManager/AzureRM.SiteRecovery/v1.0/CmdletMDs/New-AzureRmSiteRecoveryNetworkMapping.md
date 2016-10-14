---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
online version: .\Get-AzureRmSiteRecoveryNetworkMapping.md
schema: 2.0.0
---

# New-AzureRmSiteRecoveryNetworkMapping

## SYNOPSIS
Creates a mapping between virtual networks.

## SYNTAX

### EnterpriseToAzure
```
New-AzureRmSiteRecoveryNetworkMapping -PrimaryNetwork <ASRNetwork> -AzureVMNetworkId <String>
 [<CommonParameters>]
```

### EnterpriseToEnterprise
```
New-AzureRmSiteRecoveryNetworkMapping -PrimaryNetwork <ASRNetwork> -RecoveryNetwork <ASRNetwork>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRMSiteRecoveryNetworkMapping** cmdlet creates a mapping between two virtual networks and returns an azure_2 Site Recovery job to track it.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AzureVMNetworkId
Specifies the azure_2 virtual network ID.

```yaml
Type: String
Parameter Sets: EnterpriseToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryNetwork
Specifies the primary network object.

```yaml
Type: ASRNetwork
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryNetwork
Specifies the recovery network object.

```yaml
Type: ASRNetwork
Parameter Sets: EnterpriseToEnterprise
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

[Get-AzureRmSiteRecoveryNetworkMapping](.\Get-AzureRmSiteRecoveryNetworkMapping.md)

[Remove-AzureRmSiteRecoveryNetworkMapping](.\Remove-AzureRmSiteRecoveryNetworkMapping.md)

