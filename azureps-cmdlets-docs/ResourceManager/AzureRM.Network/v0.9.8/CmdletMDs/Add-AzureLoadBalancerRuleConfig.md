---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureLoadBalancerRuleConfig.md
schema: 2.0.0
---

# Add-AzureLoadBalancerRuleConfig

## SYNOPSIS
Adds a rule configuration to a load balancer.

## SYNTAX

### SetByResourceId
```
Add-AzureLoadBalancerRuleConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-FrontendIpConfigurationId <String>] [-BackendAddressPoolId <String>] [-ProbeId <String>]
 [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>]
 [-LoadDistribution <String>] [-EnableFloatingIP] [-Profile <AzureProfile>] [<CommonParameters>]
```

### SetByResource
```
Add-AzureLoadBalancerRuleConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-FrontendIpConfiguration <PSFrontendIPConfiguration>] [-BackendAddressPool <PSBackendAddressPool>]
 [-Probe <PSProbe>] [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>]
 [-IdleTimeoutInMinutes <Int32>] [-LoadDistribution <String>] [-EnableFloatingIP] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureLoadBalancerRuleConfig** cmdlet adds a rule configuration to an Azure load balancer.

## EXAMPLES

### Example 1 Add a rule configuration to a load balancer
```
PS C:\>$LoadBalancer = Get-AzureLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\> $LoadBalancer | Add-AzureLoadBalancerRuleConfig -Name "LbRuleConfig" -FrontendIPConfiguration $LoadBalancer.Properties.FrontendIPConfigurations[0] -BackendAddressPool $LoadBalancer.Properties.BackendAddressPools[0] -Probe $LoadBalancer.Properties.Probes[0] -Protocol "Tcp" -FrontendPort 80 -BackendPort 80 -IdleTimeoutInSeconds 15 -EnableFloatingIP | Set-AzureLoadBalancer
```

The first command gets the load balancer named MyLoadBalancer, and then stores it in the $LoadBalancer variable.

The second command adds the rule configuration named LbRuleConfig to the load balancer stored in $LoadBalancer, and then uses the **Set-AzureLoadBalancerRuleConfig** cmdlet to update the rule configuration for $LoadBalancer.

## PARAMETERS

### -BackendAddressPool
Specifies the backend address pool to associate with a load balancer rule configuration.

```yaml
Type: PSBackendAddressPool
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendAddressPoolId
Specifies the ID of a **BackendAddressPool** object to associate with a load balancer rule configuration.

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

### -BackendPort
Specifies the backend port for traffic that is matched by a load balancer rule configuration.

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
Specifies the length of time, in minutes, that the state of conversations is maintained in the load balancer.

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
This cmdlet adds a rule configuration to the load balancer that this parameter specifies.

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

### -LoadDistribution
Specifies a load distribution.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Default, SourceIP, SourceIPProtocol

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the load balancer rule configuration.

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

### -Probe
Specifies a probe to associate with a load balancer rule configuration.

```yaml
Type: PSProbe
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeId
Specifies the ID of the probe to associate with a load balancer rule configuration.

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
Specfies the protocol that is matched by a load balancer rule.
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

[Get-AzureLoadBalancerRuleConfig](.\Get-AzureLoadBalancerRuleConfig.md)

[New-AzureLoadBalancerRuleConfig](.\New-AzureLoadBalancerRuleConfig.md)

[Remove-AzureLoadBalancerRuleConfig](.\Remove-AzureLoadBalancerRuleConfig.md)

[Set-AzureLoadBalancerRuleConfig](.\Set-AzureLoadBalancerRuleConfig.md)

