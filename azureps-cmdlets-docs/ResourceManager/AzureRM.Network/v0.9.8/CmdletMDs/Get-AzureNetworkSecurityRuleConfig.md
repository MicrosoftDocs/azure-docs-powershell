---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureNetworkSecurityRuleConfig.md
schema: 2.0.0
---

# Get-AzureNetworkSecurityRuleConfig

## SYNOPSIS
Get a network security rule configuration for a network security group.

## SYNTAX

```
Get-AzureNetworkSecurityRuleConfig [-Name <String>] -NetworkSecurityGroup <PSNetworkSecurityGroup>
 [-DefaultRules] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureNetworkSecurityRuleConfig** cmdlet gets a network security rule configuration for an Azure network security group.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DefaultRules
Indicates whether this cmdlet gets a user-created rule configuration or a default rule configuration.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the network security rule configuration to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkSecurityGroup
Specifies a **NetworkSecurityGroup** object that contains the network security rule configuration to get.

```yaml
Type: PSNetworkSecurityGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
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

[Add-AzureNetworkSecurityRuleConfig](.\Add-AzureNetworkSecurityRuleConfig.md)

[New-AzureNetworkSecurityRuleConfig](.\New-AzureNetworkSecurityRuleConfig.md)

[Remove-AzureNetworkSecurityRuleConfig](.\Remove-AzureNetworkSecurityRuleConfig.md)

[Set-AzureNetworkSecurityRuleConfig](.\Set-AzureNetworkSecurityRuleConfig.md)

