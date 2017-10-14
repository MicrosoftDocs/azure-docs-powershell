---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
ms.assetid: 07F9EE13-9874-42FC-A17E-7615419F1381
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoveryPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoveryPolicy.md
gitcommit: https://github.com/Azure/azure-powershell/blob/1fa63f743120d7a7cd6cbb28ee43cd0f4c654af9
---

# Get-AzureRmSiteRecoveryPolicy

## SYNOPSIS
Gets Site Recovery protection policies.

## SYNTAX

### Default (Default)
```
Get-AzureRmSiteRecoveryPolicy [<CommonParameters>]
```

### ByName
```
Get-AzureRmSiteRecoveryPolicy -Name <String> [<CommonParameters>]
```

### ByFriendlyName
```
Get-AzureRmSiteRecoveryPolicy -FriendlyName <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSiteRecoveryPolicy** cmdlet gets the list of configured Azure Site Recovery protection policies or a specific protection policy by name.

## EXAMPLES

## PARAMETERS

### -FriendlyName
Specifies the friendly name of the Site Recovery replication policy.

```yaml
Type: String
Parameter Sets: ByFriendlyName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the Site Recovery replication policy.

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

### System.Collections.Generic.IEnumerable`1[Microsoft.Azure.Commands.SiteRecovery.ASRPolicy]

## NOTES

## RELATED LINKS

[New-AzureRmSiteRecoveryPolicy](./New-AzureRmSiteRecoveryPolicy.md)

[Remove-AzureRmSiteRecoveryPolicy](./Remove-AzureRmSiteRecoveryPolicy.md)
