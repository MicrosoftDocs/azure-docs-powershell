---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmLoadBalancerRuleConfig

## SYNOPSIS
Gets the rule configuration for a load balancer.

## SYNTAX

```
Get-AzureRmLoadBalancerRuleConfig [-Name <String>] -LoadBalancer <PSLoadBalancer>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Get-AzureRmLoadBalancerRuleConfig cmdlet gets one or more rule configurations for a load balancer.

## EXAMPLES

### --------------------------  Example 1 Gets the rule configuration of an existing load balancer  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $slb = Get-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName MyResourceGroup

PS C:\> Get-AzureRmLoadBalancerRuleConfig -Name "MyLBrulename" -LoadBalancer $slb
```

The first command gets the load balancer and stores it in the variable $slb.
The second command gets the associated rule configuration called MyLBrulename.

## PARAMETERS

### -Name
Specifies the name of the rule configuration to get.

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
Specifies the load balancer that is associated with the rule configuration to get.

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

[Add-AzureRmLoadBalancerRuleConfig]()

[New-AzureRmLoadBalancerRuleConfig]()

[Remove-AzureRmLoadBalancerRuleConfig]()

[Set-AzureRmLoadBalancerRuleConfig]()

