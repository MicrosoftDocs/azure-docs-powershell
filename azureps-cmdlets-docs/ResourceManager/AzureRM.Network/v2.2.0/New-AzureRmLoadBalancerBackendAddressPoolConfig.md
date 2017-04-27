---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmLoadBalancerBackendAddressPoolConfig

## SYNOPSIS
Creates a backend address pool configuration for a load balancer.

## SYNTAX

```
New-AzureRmLoadBalancerBackendAddressPoolConfig -Name <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

## DESCRIPTION
The New-AzureRmLoadBalancerBackendAddressPoolConfig cmdlet creates a backend address pool configuration for an Azure load balancer.
This pool contains network interfaces (NICs) for the virtual machines to be able to rceive traffic from the load balancer.

## EXAMPLES

### --------------------------  Example 1 Creating a new backend address pool configuration for a load balancer  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> New-AzureRmLoadBalancerBackendAddressPoolConfig -Name "BackendAddressPool02"
```

This command creates a new backend address pool configuration called "BackendAddressPool02" for a load balancer.

Name                    : BackendAddressPool02
Id                      : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroupNotSet/providers/Microsoft.Network/loadBalancers/LoadBalancerNameNotSet/backendAddressPools/BackendAddressPool02
Etag                    :
ProvisioningState       :
BackendIpConfigurations : null
LoadBalancingRules      : null

## PARAMETERS

### -Name
Specifies the name of the address pool configuration to create.

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

### -InformationAction
@{Text=}

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

[Add-AzureRmLoadBalancerBackendAddressPoolConfig]()

[Get-AzureRmLoadBalancerBackendAddressPoolConfig]()

[Remove-AzureRmLoadBalancerBackendAddressPoolConfig]()

