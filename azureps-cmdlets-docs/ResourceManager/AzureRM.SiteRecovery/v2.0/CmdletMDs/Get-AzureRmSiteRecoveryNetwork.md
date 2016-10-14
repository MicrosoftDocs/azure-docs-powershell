---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
online version: a1fe5285-5354-4e56-aed6-5e0446b07fa2
schema: 2.0.0
---

# Get-AzureRmSiteRecoveryNetwork

## SYNOPSIS
Gets information about the networks managed by Site Recovery for the current vault.

## SYNTAX

### Default (Default)
```
Get-AzureRmSiteRecoveryNetwork [<CommonParameters>]
```

### ByName
```
Get-AzureRmSiteRecoveryNetwork -Server <ASRServer> -Name <String> [<CommonParameters>]
```

### ByFriendlyName
```
Get-AzureRmSiteRecoveryNetwork -Server <ASRServer> -FriendlyName <String> [<CommonParameters>]
```

### ByServerObject
```
Get-AzureRmSiteRecoveryNetwork -Server <ASRServer> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSiteRecoveryNetwork** cmdlet gets information about Azure Site Recovery networks for the current Azure Site Recovery vault.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -FriendlyName
Specifies the friendly name of the virtual machine network.

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
Specifies the name of the virtual machine network.

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

### -Server
Specifies a Site Recovery server object.

```yaml
Type: ASRServer
Parameter Sets: ByName, ByFriendlyName, ByServerObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

