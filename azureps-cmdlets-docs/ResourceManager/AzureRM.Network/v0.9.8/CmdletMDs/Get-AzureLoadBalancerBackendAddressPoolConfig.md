---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureLoadBalancerBackendAddressPoolConfig.md
schema: 2.0.0
---

# Get-AzureLoadBalancerBackendAddressPoolConfig

## SYNOPSIS
Gets a backend address pool configuration for a load balancer.

## SYNTAX

```
Get-AzureLoadBalancerBackendAddressPoolConfig [-Name <String>] -LoadBalancer <PSLoadBalancer>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureLoadBalancerBackendAddressPoolConfig** cmdlet gets a single backend address pool or a list of backend address pools within a load balancer.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -LoadBalancer
Specifies the load balancer that is associated with the backend address pool to get.

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
Specifies the name of the load balancer that contains the backend address pool to get.

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

[Add-AzureLoadBalancerBackendAddressPoolConfig](.\Add-AzureLoadBalancerBackendAddressPoolConfig.md)

[New-AzureLoadBalancerBackendAddressPoolConfig](.\New-AzureLoadBalancerBackendAddressPoolConfig.md)

[Remove-AzureLoadBalancerBackendAddressPoolConfig](.\Remove-AzureLoadBalancerBackendAddressPoolConfig.md)

