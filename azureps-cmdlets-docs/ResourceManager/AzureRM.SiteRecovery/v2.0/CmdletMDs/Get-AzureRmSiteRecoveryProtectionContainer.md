---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
online version: 4cce9aa8-4efa-4399-b814-480a09e26f77
schema: 2.0.0
---

# Get-AzureRmSiteRecoveryProtectionContainer

## SYNOPSIS
Gets protection containers for the current Site Recovery vault.

## SYNTAX

### Default (Default)
```
Get-AzureRmSiteRecoveryProtectionContainer [<CommonParameters>]
```

### ByObjectWithName
```
Get-AzureRmSiteRecoveryProtectionContainer -Name <String> [<CommonParameters>]
```

### ByObjectWithFriendlyName
```
Get-AzureRmSiteRecoveryProtectionContainer -FriendlyName <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmSiteRecoveryProtectionContainer** cmdlet gets protection containers for the current Azure Site Recovery vault.
A protection container is a logical container for protected objects such as virtual machines.
Protection policies define replication settings for protected items and can be associated with a protection container and applied to a protected entity.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -FriendlyName
Specifies the friendly name of the protection container.

```yaml
Type: String
Parameter Sets: ByObjectWithFriendlyName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the protection container.

```yaml
Type: String
Parameter Sets: ByObjectWithName
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

