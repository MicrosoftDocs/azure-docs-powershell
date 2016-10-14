---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureLoadBalancer.md
schema: 2.0.0
---

# Add-AzureLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Adds an inbound NAT rule configuration to a load balancer.

## SYNTAX

### SetByResourceId
```
Add-AzureLoadBalancerInboundNatRuleConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-FrontendIpConfigurationId <String>] [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>]
 [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP] [-Profile <AzureProfile>] [<CommonParameters>]
```

### SetByResource
```
Add-AzureLoadBalancerInboundNatRuleConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-FrontendIpConfiguration <PSFrontendIPConfiguration>] [-Protocol <String>] [-FrontendPort <Int32>]
 [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureLoadBalancerInboundNatRuleConfig** cmdlet adds an inbound network address translation (NAT) rule configuration to an Azure load balancer.

## EXAMPLES

### Example 1: Add an inbound NAT rule configuration to a load balancer
```
PS C:\>$Lb = Get-AzureLoadBalancer -Name "myLb" -ResourceGroupName "myRg"
PS C:\> $Lb | Add-AzureLoadBalancerInboundNatRuleConfig -Name "natRule" -FrontendIPConfiguration$lb.Properties.FrontendIPConfigurations[0] -BackendIpConfiguration $Nic.Properties.IpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350 -IdleTimeoutInSeconds 17 -EnableFloatingIP | Set-AzureLoadBalancer
```

The first command gets the load balancer named myLb, and then stores it in the $Lb variable.

The second command adds an inbound NAT rule configuration to the load balancer stored in $Lb, and then uses the **Set-AzureLoadBalancer** cmdlet to update the load balancer.

## PARAMETERS

### -BackendPort
Specifies the backend port for traffic matched by a rule configuration.

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
Specifies a list of front-end IP addresses to associate with an inbound NAT rule configuration.

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
Specifies an ID for a front-end IP address configuration.

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
Specifies the front-end port that is matched by a rule configuration.

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
Specifies the length of time, in minutes, that the state of conversations is maintained in a load balancer.

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

### -LoadBalancer
Specifies a **LoadBalancer** object.
This cmdlet adds an inbound NAT rule configuration to the load balancer that this parameter specifies.

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
Specifies the name of the inbound NAT rule configuration to add.

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
Specifies the protocol that is matched by an inbound NAT rule.
The acceptable values for this parameter are:Tcp or Udp.

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

[Get-AzureLoadBalancer](.\Get-AzureLoadBalancer.md)

[Get-AzureLoadBalancerInboundNatRuleConfig](.\Get-AzureLoadBalancerInboundNatRuleConfig.md)

[New-AzureLoadBalancerInboundNatRuleConfig](.\New-AzureLoadBalancerInboundNatRuleConfig.md)

[Remove-AzureLoadBalancerInboundNatRuleConfig](.\Remove-AzureLoadBalancerInboundNatRuleConfig.md)

[Set-AzureLoadBalancer](.\Set-AzureLoadBalancer.md)

[Set-AzureLoadBalancerInboundNatRuleConfig](.\Set-AzureLoadBalancerInboundNatRuleConfig.md)

