---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureLoadBalancerInboundNatRuleConfig.md
schema: 2.0.0
---

# New-AzureLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Creates an inbound NAT rule configuration for a load balancer.

## SYNTAX

### SetByResourceId
```
New-AzureLoadBalancerInboundNatRuleConfig -Name <String> [-FrontendIpConfigurationId <String>]
 [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>]
 [-EnableFloatingIP] [-Profile <AzureProfile>] [<CommonParameters>]
```

### SetByResource
```
New-AzureLoadBalancerInboundNatRuleConfig -Name <String> [-FrontendIpConfiguration <PSFrontendIPConfiguration>]
 [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>]
 [-EnableFloatingIP] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureLoadBalancerInboundNatRuleConfig** cmdlet creates an inbound network address translation (NAT) rule configuration for an Azure load balancer.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -BackendPort
Specifies the backend port for traffic that is matched by this rule configuration.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFloatingIP
Indicates that this cmdlet enables a floating IP address for a rule configuration.

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

### -FrontendIpConfiguration
Specifies a list of front-end IP addresses to associate with a load balancer rule configuration.

```yaml
Type: PSFrontendIPConfiguration
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendIpConfigurationId
Specifies the ID for a front-end IP address configuration.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendPort
Specifies the front-end port that is matched by a load balancer rule configuration.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeoutInMinutes
Specifies the length of time, in minutes, for which the state of conversations is maintained in a load balancer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the rule configuration to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -Protocol
Specifies a protocol.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Tcp, Udp

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

[Get-AzureLoadBalancerInboundNatRuleConfig](.\Get-AzureLoadBalancerInboundNatRuleConfig.md)

[Remove-AzureLoadBalancerInboundNatRuleConfig](.\Remove-AzureLoadBalancerInboundNatRuleConfig.md)

[Set-AzureLoadBalancerInboundNatRuleConfig](.\Set-AzureLoadBalancerInboundNatRuleConfig.md)

