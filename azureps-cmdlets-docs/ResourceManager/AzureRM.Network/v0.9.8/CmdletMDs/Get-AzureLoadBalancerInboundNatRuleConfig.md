---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureLoadBalancerInboundNatRuleConfig.md
schema: 2.0.0
---

# Get-AzureLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Gets an inbound NAT rule configuration for a load balancer.

## SYNTAX

```
Get-AzureLoadBalancerInboundNatRuleConfig [-Name <String>] -LoadBalancer <PSLoadBalancer>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureLoadBalancerInboundNatRuleConfig** cmdlet gets one or more inbound network address translation (NAT) rules in an Azure load balancer.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -LoadBalancer
Specifies the load balancer that is associated with the inbound NAT rule configuration to get.

```yaml
Type: PSLoadBalancer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the inbound NAT rule configuration to get.

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

[Add-AzureLoadBalancerInboundNatRuleConfig](.\Add-AzureLoadBalancerInboundNatRuleConfig.md)

[New-AzureLoadBalancerInboundNatRuleConfig](.\New-AzureLoadBalancerInboundNatRuleConfig.md)

[Remove-AzureLoadBalancerInboundNatRuleConfig](.\Remove-AzureLoadBalancerInboundNatRuleConfig.md)

[Set-AzureLoadBalancerInboundNatRuleConfig](.\Set-AzureLoadBalancerInboundNatRuleConfig.md)

