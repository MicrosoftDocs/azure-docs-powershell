---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
online version: .\Remove-AzureRmSiteRecoveryServer.md
schema: 2.0.0
---

# Get-AzureRmSiteRecoveryServer

## SYNOPSIS
Gets information about Site Recovery servers registered to the current vault.

## SYNTAX

### Default (Default)
```
Get-AzureRmSiteRecoveryServer [<CommonParameters>]
```

### ByName
```
Get-AzureRmSiteRecoveryServer -Name <String> [<CommonParameters>]
```

### ByFriendlyName
```
Get-AzureRmSiteRecoveryServer -FriendlyName <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSiteRecoveryServer** cmdlet gets information about azure_2 Site Recovery servers registered to the current Site Recovery vault.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -FriendlyName
Specifies the friendly name of the server.

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
Specifies the name of the server.

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

[Remove-AzureRmSiteRecoveryServer](.\Remove-AzureRmSiteRecoveryServer.md)

