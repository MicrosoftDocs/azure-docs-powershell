---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRmLoadBalancer

## SYNOPSIS
Creates a load balancer.

## SYNTAX

```
New-AzureRmLoadBalancer -Name <String> -ResourceGroupName <String> -Location <String>
 [-FrontendIpConfiguration <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSFrontendIPConfiguration]>]
 [-BackendAddressPool <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool]>]
 [-Probe <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSProbe]>]
 [-InboundNatRule <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSInboundNatRule]>]
 [-LoadBalancingRule <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSLoadBalancingRule]>]
 [-Tag <Hashtable[]>]
 [-InboundNatPool <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSInboundNatPool]>]
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmLoadBalancer cmdlet creates an Azure load balancer.
Configuring a load balancer leads to providing higher availability for workloads in Azure.
A load balancer distributes traffic among healthy services or virtual machines defined in a load balancer set.

## EXAMPLES

### --------------------------  Example 1 Create a Load Balancer  --------------------------

```
PS C:\> $publicip = New-AzureRmPublicIpAddress -ResourceGroupName MyResourceGroup -name MyPublicIp -location 'West US' -AllocationMethod Dynamic
PS C:\> $frontend = New-AzureRmLoadBalancerFrontendIpConfig -Name MyFrontEnd -PublicIpAddress $publicip
PS C:\> $backendAddressPool = New-AzureRmLoadBalancerBackendAddressPoolConfig -Name MyBackendAddPoolConfig02
PS C:\> $probe = New-AzureRmLoadBalancerProbeConfig -Name MyProbe -Protocol http -Port 80 -IntervalInSeconds 15 -ProbeCount 2 -RequestPath healthcheck.aspx
PS C:\> $inboundNatRule1 = New-AzureRmLoadBalancerInboundNatRuleConfig -Name MyinboundNatRule1 -FrontendIPConfiguration $frontend -Protocol Tcp -FrontendPort 3389 -BackendPort 3389 -IdleTimeoutInMinutes 15 -EnableFloatingIP
PS C:\> $inboundNatRule2 = New-AzureRmLoadBalancerInboundNatRuleConfig -Name MyinboundNatRule2 -FrontendIPConfiguration $frontend -Protocol Tcp -FrontendPort 3391 -BackendPort 3392
PS C:\> $lbrule = New-AzureRmLoadBalancerRuleConfig -Name MyLBruleName -FrontendIPConfiguration $frontend -BackendAddressPool $backendAddressPool -Probe $probe -Protocol Tcp -FrontendPort 80 -BackendPort 80 -IdleTimeoutInMinutes 15 -EnableFloatingIP -LoadDistribution SourceIP
PS C:\> $lb = New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName MyResourceGroup -Location 'West US' -FrontendIpConfiguration $frontend -BackendAddressPool $backendAddressPool -Probe $probe -InboundNatRule $inboundNatRule1,$inboundNatRule2 -LoadBalancingRule $lbrule
PS C:\> Get-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName MyResourceGroup
```

Since deploying a load balancer requires certain objects to be created, this examples shows you how to create them.
The second to last command creates a load balancer called MyLoadBalancer within resource group MyResourceGroup.
And the last command is a get to ensure it was successfully created.
Note that thios example only shows how to create a load balancer and it must be configured using Add-AzureRmVirtualNetworkInterface to assign the NICs to different VMs.

```
Name                     : MyLoadBalancer
ResourceGroupName        : MyResourceGroup
Location                 : westus

Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/res
                           ourceGroups/MyResourceGroup/providers/Microsoft.Network/loadBa
                           lancers/MyLoadBalancer
Etag                     : W/"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
ResourceGuid             : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded
Tags                     :
FrontendIpConfigurations : [
                             {
                               "Name": "MyFrontEnd",
                               "Etag":
                           "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
                               /resourceGroups/MyResourceGroup/providers/Microsoft.Net
                           work/loadBalancers/MyLoadBalancer/frontendIPConfigurations/My
                           FrontEnd",
                               "PrivateIpAllocationMethod": "Dynamic",
                               "PublicIpAddress": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
                                 x/resourceGroups/MyResourceGroup/providers/Microsoft.N
                           etwork/publicIPAddresses/MyPublicIP"
                               },
                               "ProvisioningState": "Succeeded",
                               "InboundNatRules": \[
                                 {
                                   "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft
                           .Network/loadBalancers/MyLoadBalancer/inboundNatRules/Myinbou
                           ndNatRule1"
                                 },
                                 {
                                   "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft
                           .Network/loadBalancers/MyLoadBalancer/inboundNatRules/Myinbou
                           ndNatRule2"
                                 }
                               \],
                               "LoadBalancingRules": \[
                                 {
                                   "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft
                           .Network/loadBalancers/MyLoadBalancer/loadBalancingRules/MyLB
                           ruleName"
                                 }
                               \],
                               "InboundNatPools": \[\]
                             }
                           \]
BackendAddressPools      : \[
                             {
                               "Name": "MyBackendAddPoolConfig02",
                               "Etag":
                           "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Net
                           work/loadBalancers/MyLoadBalancer/backendAddressPools/MyBacke
                           ndAddPoolConfig02",
                               "BackendIpConfigurations": \[\],
                               "LoadBalancingRules": \[
                                 {
                                   "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft
                           .Network/loadBalancers/MyLoadBalancer/loadBalancingRules/MyLB
                           ruleName"
                                 }
                               \],
                               "ProvisioningState": "Succeeded"
                             }
                           \]
LoadBalancingRules       : \[
                             {
                               "Name": "MyLBruleName",
                               "Etag":
                           "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Net
                           work/loadBalancers/MyLoadBalancer/loadBalancingRules/MyLBrule
                           Name",
                               "BackendAddressPool": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.N
                           etwork/loadBalancers/MyLoadBalancer/backendAddressPools/MyBac
                           kendAddPoolConfig02"
                               },
                               "Probe": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.N
                           etwork/loadBalancers/MyLoadBalancer/probes/MyProbe"
                               },
                               "FrontendPort": 80,
                               "IdleTimeoutInMinutes": 15,
                               "LoadDistribution": "SourceIP",
                               "EnableFloatingIP": true,
                               "FrontendIPConfiguration": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.N
                           etwork/loadBalancers/MyLoadBalancer/frontendIPConfigurations/
                           MyFrontEnd"
                               },
                               "BackendPort": 80,
                               "Protocol": "Tcp",
                               "ProvisioningState": "Succeeded"
                             }
                           \]
Probes                   : \[
                             {
                               "Name": "MyProbe",
                               "Etag":
                           "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Net
                           work/loadBalancers/MyLoadBalancer/probes/MyProbe",
                               "LoadBalancingRules": \[
                                 {
                                   "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft
                           .Network/loadBalancers/MyLoadBalancer/loadBalancingRules/MyLB
                           ruleName"
                                 }
                               \],
                               "Protocol": "Http",
                               "Port": 80,
                               "IntervalInSeconds": 15,
                               "NumberOfProbes": 2,
                               "RequestPath": "healthcheck.aspx",
                               "ProvisioningState": "Succeeded"
                             }
                           \]
InboundNatRules          : \[
                             {
                               "Name": "MyinboundNatRule1",
                               "Etag":
                           "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Net
                           work/loadBalancers/MyLoadBalancer/inboundNatRules/MyinboundNa
                           tRule1",
                               "FrontendPort": 3389,
                               "IdleTimeoutInMinutes": 15,
                               "EnableFloatingIP": true,
                               "FrontendIPConfiguration": {
                                 "Id": "/subscriptions/3xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.N
                           etwork/loadBalancers/MyLoadBalancer/frontendIPConfigurations/
                           MyFrontEnd"
                               },
                               "BackendPort": 3389,
                               "Protocol": "Tcp",
                               "ProvisioningState": "Succeeded"
                             },
                             {
                               "Name": "MyinboundNatRule2",
                               "Etag":
                           "W/\"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx\"",
                               "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Net
                           work/loadBalancers/MyLoadBalancer/inboundNatRules/MyinboundNa
                           tRule2",
                               "FrontendPort": 3391,
                               "IdleTimeoutInMinutes": 4,
                               "EnableFloatingIP": false,
                               "FrontendIPConfiguration": {
                                 "Id": "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.N
                           etwork/loadBalancers/MyLoadBalancer/frontendIPConfigurations/
                           MyFrontEnd"
                               },
                               "BackendPort": 3392,
                               "Protocol": "Tcp",
                               "ProvisioningState": "Succeeded"
                             }
                           \]
InboundNatPools          : \[\]
```

## PARAMETERS

### -Name
Specifies the name of the load balancer to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group in which to create a load balancer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the region in which to create a load balancer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FrontendIpConfiguration
Specifies a list of front-end IP addresses to associate with a load balancer.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSFrontendIPConfiguration]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendAddressPool
Specifies a backend address pool to associate with a load balancer.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSBackendAddressPool]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Probe
Specifies a list of probes to associate with a load balancer.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSProbe]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InboundNatRule
Specifies a list of inbound network address translation (NAT) rules to associate with a load balancer.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSInboundNatRule]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LoadBalancingRule
Specifies a list of load balancing rules to associate with a load balancer.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSLoadBalancingRule]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies an array of tags to associate with a load balancer.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InboundNatPool
@{Text=}

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSInboundNatPool]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet creates a load balancer even if a load balancer with the same name already exists.

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

### -WhatIf

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmLoadBalancer]()

[Remove-AzureRmLoadBalancer]()

[Set-AzureRmLoadBalancer]()
