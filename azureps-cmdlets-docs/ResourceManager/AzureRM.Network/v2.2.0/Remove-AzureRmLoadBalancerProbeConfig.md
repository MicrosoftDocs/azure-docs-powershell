---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmLoadBalancerProbeConfig

## SYNOPSIS
Removes a probe configuration from a load balancer.

## SYNTAX

```
Remove-AzureRmLoadBalancerProbeConfig [-Name <String>] -LoadBalancer <PSLoadBalancer> [<CommonParameters>]
```

## DESCRIPTION
The Remove-AzureRmLoadBalancerProbeConfig cmdlet removes a probe configuration from a load balancer.

## EXAMPLES

### --------------------------  Example 1: Removing an existing probe configuration of a load balancer  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\> $loadbalancer = Get-AzureRmLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"

PS C:> Remove-AzureRmLoadBalancerProbeConfig -Name "MyProbe" -LoadBalancer $loadbalancer
```

The first command loads the existing load balancer "MyLoadBalancer" with associated probe configuration called "MyProbe." The second command deletes the configuration.

## PARAMETERS

### -Name
Specifies the name of the probe configuration to remove.

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

### -LoadBalancer
Specifies the load balancer that contains the probe configuration to remove.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmLoadBalancerProbeConfig]()

[Get-AzureRmLoadBalancerProbeConfig]()

[New-AzureRmLoadBalancerProbeConfig]()

[Set-AzureRmLoadBalancerProbeConfig]()

