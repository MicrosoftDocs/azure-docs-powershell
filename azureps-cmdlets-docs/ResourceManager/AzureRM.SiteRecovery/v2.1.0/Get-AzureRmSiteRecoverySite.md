---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0A6BE7ED-CFB5-4527-8A13-F5165807FB01
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

### 1:
```

```

## PARAMETERS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureRmSiteRecoverySite](./New-AzureRmSiteRecoverySite.md)

[Remove-AzureRmSiteRecoverySite](./Remove-AzureRmSiteRecoverySite.md)


