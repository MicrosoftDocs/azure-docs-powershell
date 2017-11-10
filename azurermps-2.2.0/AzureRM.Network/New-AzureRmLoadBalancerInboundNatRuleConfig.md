---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmLoadBalancerInboundNatRuleConfig

## SYNOPSIS
Creates an inbound NAT rule configuration for a load balancer.

## SYNTAX

### SetByResourceId
```
New-AzureRmLoadBalancerInboundNatRuleConfig -Name <String> [-FrontendIpConfigurationId <String>]
 [-Protocol <String>] [-FrontendPort <Int32>] [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>]
 [-EnableFloatingIP] [<CommonParameters>]
```

### SetByResource
```
New-AzureRmLoadBalancerInboundNatRuleConfig -Name <String>
 [-FrontendIpConfiguration <PSFrontendIPConfiguration>] [-Protocol <String>] [-FrontendPort <Int32>]
 [-BackendPort <Int32>] [-IdleTimeoutInMinutes <Int32>] [-EnableFloatingIP] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmLoadBalancerInboundNatRuleConfig cmdlet creates an inbound network address translation (NAT) rule configuration for an Azure load balancer.
These rules control how traffic coming to the frontend IP of the load balancer is forwarded to private IP of a virtual machine behind the load balancer.

## EXAMPLES

### --------------------------  Example 1: Creating a new inbound NAT rule for a load balancer  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\> $publicip = New-AzureRmPublicIpAddress -ResourceGroupName "MyResourceGroup" -name "MyPublicIP" -location 'West US' -AllocationMethod Dynamic
PS C:\> $frontend = New-AzureRmLoadBalancerFrontendIpConfig -Name "FrontendIpConfig01"-PublicIpAddress $publicip
PS C:\> New-AzureRmLoadBalancerInboundNatRuleConfig -Name MyInboundNatRule -FrontendIPConfiguration $frontend -Protocol Tcp -FrontendPort 3389 -BackendPort 3389
```

The first command creates a new public IP address within resource group "MyResourceGroup" called "MyPublicIP" in west US and stores it in the object publicip.
In order to create an inbound NAT rule, a front end IP configuration is needed as shown in the second command.
However, one needs a public IP in order to create this frontend IP configuration.
This is accomplished in the first two commands.
Finally, a new inbound NAT rule configuration is created in the third command called MyInboundNatRule using the frontend object created in the second command.
Further, a Tcp protocol is used and the frontend port is 3389, the same as the backend in this case.
Note that frontendIpConfiguration, Procotol, frontendPort and backendPort are all required to create a new inbound NAT rule configuration.

Below is some sample output:
Note that this may not show up if you store the InboundNatRuleConfig in an object.

Name                    : MyInboundNatRule
Id                      : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroupNotSet/providers/Microsoft.Network/loadBalancers/LoadBalancerNameNotSet/inboundNatRules/MyInboundNatRule
Etag                    :
ProvisioningState       :
Protocol                : Tcp
FrontendPort            : 3389
BackendPort             : 3389
IdleTimeoutInMinutes    :
EnableFloatingIP        : False
FrontendIPConfiguration : {
                            "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroupNotSet/providers/Microsoft.Network/loadBalancers/LoadBalancerNameNotSet/frontendIPConfigurations/Fronten
                          dIpConfig01"
                          }
BackendIPConfiguration  : null

## PARAMETERS

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

### -Protocol
Specifies a protocol.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmLoadBalancerInboundNatRuleConfig]()

[Get-AzureRmLoadBalancerInboundNatRuleConfig]()

[Remove-AzureRmLoadBalancerInboundNatRuleConfig]()

[Set-AzureRmLoadBalancerInboundNatRuleConfig]()

