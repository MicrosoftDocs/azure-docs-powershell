---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureLoadBalancerProbeConfig.md
schema: 2.0.0
---

# Get-AzureLoadBalancerProbeConfig

## SYNOPSIS
Gets a probe configuration for a load balancer.

## SYNTAX

```
Get-AzureLoadBalancerProbeConfig [-Name <String>] -LoadBalancer <PSLoadBalancer> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureLoadBalancerProbeConfig** cmdlet gets one or more probe configurations for a load balancer.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -LoadBalancer
Specifies the load balancer that is associated with the probe configuration to get.

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
Specifies the name of the probe configuration to get.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureLoadBalancerProbeConfig](.\Add-AzureLoadBalancerProbeConfig.md)

[New-AzureLoadBalancerProbeConfig](.\New-AzureLoadBalancerProbeConfig.md)

[Remove-AzureLoadBalancerProbeConfig](.\Remove-AzureLoadBalancerProbeConfig.md)

[Set-AzureLoadBalancerProbeConfig](.\Set-AzureLoadBalancerProbeConfig.md)

