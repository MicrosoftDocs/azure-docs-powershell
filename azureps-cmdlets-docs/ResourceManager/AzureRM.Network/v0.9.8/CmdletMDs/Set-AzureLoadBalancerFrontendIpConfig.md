---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureLoadBalancerFrontendIpConfig.md
schema: 2.0.0
---

# Set-AzureLoadBalancerFrontendIpConfig

## SYNOPSIS
Sets the goal state for a front-end IP configuration in a load balancer.

## SYNTAX

### SetByResourceId
```
Set-AzureLoadBalancerFrontendIpConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-PrivateIpAddress <String>] [-SubnetId <String>] [-PublicIpAddressId <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SetByResource
```
Set-AzureLoadBalancerFrontendIpConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-PrivateIpAddress <String>] [-Subnet <PSSubnet>] [-PublicIpAddress <PSPublicIpAddress>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureLoadBalancerFrontendIpConfig** cmdlet sets the goal state for a front-end IP configuration in an Azure load balancer.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -LoadBalancer
Specifies a load balancer.
This cmdlet sets the goal state for a front-end configuration for the load balancer that this parameter specifies.

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
Specifies the name of the front-end IP configuration to set.

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

### -PrivateIpAddress
Specifies the private IP address of the load balancer that is associated with the front-end IP configuration to set.
Specify this parameter only if you also specify the **Subnet** parameter.

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

### -PublicIpAddress
Specifies the **PublicIpAddress** object that is associated with the front-end IP configuration to set.

```yaml
Type: PSPublicIpAddress
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIpAddressId
Specifies the ID of the **PublicIpAddress** object that is associated with the front-end IP configuration to set.

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

### -Subnet
Specifies the **Subnet** object that contains the front-end IP configuration to set.

```yaml
Type: PSSubnet
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Specifies the ID of the subnet that contains the front-end IP configuration to set.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureLoadBalancerFrontendIpConfig](.\Add-AzureLoadBalancerFrontendIpConfig.md)

[Get-AzureLoadBalancerFrontendIpConfig](.\Get-AzureLoadBalancerFrontendIpConfig.md)

[New-AzureLoadBalancerFrontendIpConfig](.\New-AzureLoadBalancerFrontendIpConfig.md)

[Remove-AzureLoadBalancerFrontendIpConfig](.\Remove-AzureLoadBalancerFrontendIpConfig.md)

