---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
ms.assetid: F9A652D0-26D9-4F3F-A365-285B05AA7C0B
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoverySite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Get-AzureRmSiteRecoverySite.md
gitcommit: https://github.com/Azure/azure-powershell/blob/94e42834e29c78cafba9e3f1e99e14af92561036
---

# Get-AzureRmSiteRecoverySite

## SYNOPSIS
Gets the Hyper-V sites from the Site Recovery vault.

## SYNTAX

### Default (Default)
```
Get-AzureRmSiteRecoverySite [<CommonParameters>]
```

### ByName
```
Get-AzureRmSiteRecoverySite -Name <String> [<CommonParameters>]
```

### ByFriendlyName
```
Get-AzureRmSiteRecoverySite -FriendlyName <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSiteRecoverySite** cmdlet gets the Hyper-V sites in the Azure Site Recovery vault.

## EXAMPLES

## PARAMETERS

### -Name
Specifies the name of the site.

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

### -FriendlyName
Specifies the friendly name of the site.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureRmSiteRecoverySite](./New-AzureRmSiteRecoverySite.md)

[Remove-AzureRmSiteRecoverySite](./Remove-AzureRmSiteRecoverySite.md)
