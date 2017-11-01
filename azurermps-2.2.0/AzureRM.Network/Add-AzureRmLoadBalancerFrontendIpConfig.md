---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureRmLoadBalancerFrontendIpConfig

## SYNOPSIS
Adds a front-end IP configuration to a load balancer.

## SYNTAX

### SetByResourceId
```
Add-AzureRmLoadBalancerFrontendIpConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-PrivateIpAddress <String>] [-SubnetId <String>] [-PublicIpAddressId <String>] [<CommonParameters>]
```

### SetByResource
```
Add-AzureRmLoadBalancerFrontendIpConfig -Name <String> -LoadBalancer <PSLoadBalancer>
 [-PrivateIpAddress <String>] [-Subnet <PSSubnet>] [-PublicIpAddress <PSPublicIpAddress>] [<CommonParameters>]
```

## DESCRIPTION
The Add-AzureRmLoadBalancerFrontendIpConifg cmdlet adds a front-end IP configuration to an Azure load balancer.
This frontend IP configuration contains public IP addresses for incoming network traffic.

## EXAMPLES

### --------------------------  Example 1 Add a frontend IP configuration with a dynamic IP address  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$Subnet = Get-AzureRmVirtualNetwork -Name "myVnet" -ResourceGroupName "myRg" | Get-AzureRmVirtualNetworkSubnetConfig -Name "mysubnet"
PS C:\> Get-AzureRmLoadBalancer -Name "myLB" -ResourceGroupName "NrpTest" | Add-AzureRmLoadBalancerFrontendIpConfig -Name "frontendName" -Subnet $Subnet | Set-AzureRmLoadBalancer
```

This command adds a front-end IP configuration to the load balancer with a dynamic private IP address from the specified subnet.

Name                     : myLB
ResourceGroupName        : NrpTest
Location                 : westus
Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGr
                           oups/NrpTest/providers/Microsoft.Network/loadBalancers/myLB
Etag                     : W/"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ResourceGuid             : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded
Tags                     :
FrontendIpConfigurations : \[
                             {
                               "Name": "frontendName",
                               "Etag": "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
                           /resourceGroups/NrpTest/providers/Microsoft.Network/loadBalan
                           cers/myLB/frontendIPConfigurations/frontendName",
                               "PrivateIpAddress": "XX.X.X.XX",
                               "PrivateIpAllocationMethod": "Dynamic",
                               "Subnet": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/NrpTest/providers/Microsoft.Network/virtual
                           Networks/myVnet/subnets/mysubnet"
                               },
                               "ProvisioningState": "Succeeded",
                               "InboundNatRules": \[\],
                               "LoadBalancingRules": \[\],
                               "InboundNatPools": \[\]
                             }
                           \]
BackendAddressPools      : \[\]
LoadBalancingRules       : \[\]
Probes                   : \[\]
InboundNatRules          : \[\]
InboundNatPools          : \[\]

### --------------------------  Example 2 Add a frontend IP configuration with a static IP address  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$Subnet = Get-AzureRmVirtualNetwork -Name "myVnet" -ResourceGroupName "myRg" | Get-AzureRmVirtualNetworkSubnetConfig -Name "mysubnet"
PS C:\> Get-AzureRmLoadBalancer -Name "myLB" -ResourceGroupName "NrpTest" | Add-AzureRmLoadBalancerFrontendIpConfig -Name "frontendName" -Subnet $Subnet -PrivateIpAddress "10.0.1.6" | Set-AzureRmLoadBalancer
```

This command adds a front-end IP configuration to the load balancer with a static private IP address from the specified subnet.

Name                     : myLB
ResourceGroupName        : NrpTest
Location                 : westus
Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGr
                           oups/NrpTest/providers/Microsoft.Network/loadBalancers/myLB
Etag                     : W/"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ResourceGuid             : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded
Tags                     :
FrontendIpConfigurations : \[
                             {
                               "Name": "frontendName",
                               "Etag": "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
                           /resourceGroups/NrpTest/providers/Microsoft.Network/loadBalan
                           cers/myLB/frontendIPConfigurations/frontendName",
                               "PrivateIpAddress": "10.0.1.6",
                               "PrivateIpAllocationMethod": "Static",
                               "Subnet": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/NrpTest/providers/Microsoft.Network/virtual
                           Networks/myVnet/subnets/mysubnet"
                               },
                               "ProvisioningState": "Succeeded",
                               "InboundNatRules": \[\],
                               "LoadBalancingRules": \[\],
                               "InboundNatPools": \[\]
                             }
                           \]
BackendAddressPools      : \[\]
LoadBalancingRules       : \[\]
Probes                   : \[\]
InboundNatRules          : \[\]
InboundNatPools          : \[\]

### --------------------------  Example 3 Add a frontend IP configuration with a public IP address  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$PublicIp = Get-AzureRmPublicIpAddress -ResourceGroupName "myRG" -Name "myPub"
PS C:\> Get-AzureRmLoadBalancer -Name "myLB" -ResourceGroupName "NrpTest" | Add-AzureRmLoadBalancerFrontendIpConfig -Name "frontendName" -PublicIpAddress $PublicIp | Set-AzureRmLoadBalancer
```

This command adds a front-end IP configuration to the load balancer with a public IP address.

## PARAMETERS

### -Name
Specifies the name of the front-end IP configuration to add.

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
This cmdlet adds a front-end IP configuration to the load balancer that this parameter specifies.

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

### -PrivateIpAddress
Specifies the PublicIpAddress object to associate with a front-end IP configuration.

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

### -SubnetId
Specifies the ID of the subnet in which to add a front-end IP configuration.

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

### -PublicIpAddressId
Specifies the ID of the PublicIpAddress object to associate with a front-end IP configuration.

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
Specifies the Subnet object in which to add a front-end IP configuration.

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

### -PublicIpAddress
Specifies the PublicIpAddress object to associate with a front-end IP configuration.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmLoadBalancerFrontendIpConfig]()

[Get-AzureRmVirtualNetwork]()

[Get-AzureRmVirtualNetworkSubnetConfig]()

[New-AzureRmLoadBalancerFrontendIpConfig]()

[Remove-AzureRmLoadBalancerFrontendIpConfig]()

[Set-AzureRmLoadBalancerFrontendIpConfig]()

