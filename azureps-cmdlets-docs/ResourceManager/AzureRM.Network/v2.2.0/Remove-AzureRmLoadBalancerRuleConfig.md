---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmLoadBalancerRuleConfig

## SYNOPSIS
Removes a rule configuration for a load balancer.

## SYNTAX

```
Remove-AzureRmLoadBalancerRuleConfig [-Name <String>] -LoadBalancer <PSLoadBalancer>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Remove-AzureRmLoadBalancerRuleConfig cmdlet removes a rule configuration for an Azure load balancer.

## EXAMPLES

### --------------------------  Example 1 Deleting a rule configuration associated with a load balancer  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $loadbalancer = Get-AzureRmLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"

PS C:> Remove-AzureRmLoadBalancerRuleConfig -Name  "MyLBruleName" -LoadBalancer $loadbalancer
```

The first command loads the existing load balancer "MyLoadBalancer" with associated load balancing rule configuration called "MyLBruleName." The second command deletes the configuration.

## PARAMETERS

### -Name
Specifies the name of the load balancer rule configuration to remove.

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
Specifies the LoadBalancer object that contains the rule configuration to remove.

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

[Get-AzureRmLoadBalancerRuleConfig]()

[New-AzureRmLoadBalancerRuleConfig]()

[Set-AzureRmLoadBalancerRuleConfig]()

