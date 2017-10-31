---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureRmLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Adds an inbound NAT rule configuration to a load balancer.

## SYNTAX

### SetByResourceId
```
Add-AzureRmLoadBalancerInboundNatRuleConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-FrontendIpConfigurationId <String>] [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>]
 [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP] [<CommonParameters>]
```

### SetByResource
```
Add-AzureRmLoadBalancerInboundNatRuleConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-FrontendIpConfiguration <PSFrontendIPConfiguration>] [-Protocol <String>] [-FrontendPort <Int32>]
 [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP] [<CommonParameters>]
```

## DESCRIPTION
The Add-AzureRmLoadBalancerInboundNatRuleConfig cmdlet adds an inbound network address translation rule configuration to an Azure load balancer.
This configuration contains rules mapping a public port on the load balancer to a port for a specific virtual machine in the backend address pool.

## EXAMPLES

### --------------------------  Example 1: Add an inbound NAT rule configuration to a load balancer  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\> $slb = Get-AzureRmLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"

PS C:\> $slb | Add-AzureRmLoadBalancerInboundNatRuleConfig -Name "NewNatRule" -FrontendIPConfiguration $slb.FrontendIpConfigurations[0] -Protocol "Tcp" -FrontendPort 3350 -BackendPort 3350  -EnableFloatingIP
```

The first command stores the existing load balancer called "MyloadBalancer" into a varibale called $slb.
The second command then adds an Inbound NAT rule configuration with appropriate details.
Note that these are chosen as an example and these may change based on one's loadbalancer.

Name                     : MyLoadBalancer
ResourceGroupName        : MyResourceGroup
Location                 : westus
Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Network/loadBalancers/MyLoadBalancer
Etag                     : W/"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
ResourceGuid             : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded
Tags                     : 
FrontendIpConfigurations : \[\]
BackendAddressPools      : \[\]
LoadBalancingRules       : \[\]
Probes                   : \[\]
InboundNatRules          : \[
                             
                             {
                               "Name": "NewNatRule",
                               "Etag": "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Network/loadBalancers/MyLoadBalancer/inbo
                           undNatRules/NewRule",
                               "FrontendPort": 81,
                               "IdleTimeoutInMinutes": 4,
                               "EnableFloatingIP": true,
                               "FrontendIPConfiguration": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Network/loadBalancers/MyLoadBalancer/fr
                           ontendIPConfigurations/MyFrontEnd"
                               },
                               "BackendPort": 8181,
                               "Protocol": "Tcp",
                               "ProvisioningState": "Succeeded"
                             }
                           \]
InboundNatPools          : \[\]

## PARAMETERS

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

### -LoadBalancer
Specifies a LoadBalancer object.
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

### -Protocol
Specifies the protocol that is matched by an inbound NAT rule.
The acceptable values for this parameter are:Tcp or Udp.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmLoadBalancer]()

[Get-AzureRmLoadBalancerInboundNatRuleConfig]()

[New-AzureRmLoadBalancerInboundNatRuleConfig]()

[Remove-AzureRmLoadBalancerInboundNatRuleConfig]()

[Set-AzureRmLoadBalancer]()

[Set-AzureRmLoadBalancerInboundNatRuleConfig]()

