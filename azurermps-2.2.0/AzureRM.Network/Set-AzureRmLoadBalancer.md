---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmLoadBalancer

## SYNOPSIS
Sets the goal state for a load balancer.

## SYNTAX

```
Set-AzureRmLoadBalancer -LoadBalancer <PSLoadBalancer> [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureRmLoadBalancer cmdlet sets the goal state for an Azure load balancer.
This cmdlet is especially helpful when load balancer configurations may need to be changed or updated.

## EXAMPLES

### --------------------------  1: Update an existing load balancer  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> $slb = Get-AzureRmLoadBalancer -Name NRPLB -ResourceGroupName NRP-RG

PS C:\> $slb | Add-AzureRmLoadBalancerInboundNatRuleConfig -Name NewRule -FrontendIpConfiguration $slb.FrontendIpConfigurations[0] -FrontendPort 81  -BackendPort 8181 -Protocol TCP

PS C:\> $slb | Set-AzureRmLoadBalancer
```

Using an existing load balancer called NRPLB which is assigned to variable $slb in the first command, the second command is then used to add a new inbound NAT rule called "NewRule" using port 81 in the front end and port 8181 as the backend pool to this existing load balancer.
The third command then saves and updates the configuration using the Set-AzureRmLoadBalancer cmdlet.

Below is example output to ensure the update of NewRule was successful.
Note that this output may look different depending on your load balancer configurations.

Name                     : NRPLB
ResourceGroupName        : NRP-RG
Location                 : westus
Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGro
                           ups/NRP-RG/providers/Microsoft.Network/loadBalancers/NRPLB
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
                               "Name": "NewRule",
                               "Etag": "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/
                           resourceGroups/NRP-RG/providers/Microsoft.Network/loadBalance
                           rs/NRPLB/inboundNatRules/NewRule",
                               "FrontendPort": 81,
                               "IdleTimeoutInMinutes": 4,
                               "EnableFloatingIP": false,
                               "FrontendIPConfiguration": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
                           f/resourceGroups/NRP-RG/providers/Microsoft.Network/loadBalan
                           cers/NRPLB/frontendIPConfigurations/MyFrontEnd"
                               },
                               "BackendPort": 8181,
                               "Protocol": "Tcp",
                               "ProvisioningState": "Succeeded"
                             }
                           \]
InboundNatPools          : \[\]

## PARAMETERS

### -LoadBalancer
Specifies a load balancer.
This cmdlet sets the goal state for the load balancer that this parameter specifies.

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

[Get-AzureRmLoadBalancer]()

[New-AzureRmLoadBalancer]()

[Remove-AzureRmLoadBalancer]()

