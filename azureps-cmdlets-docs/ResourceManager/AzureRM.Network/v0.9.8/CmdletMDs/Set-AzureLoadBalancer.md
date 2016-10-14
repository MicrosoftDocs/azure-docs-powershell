---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureLoadBalancer.md
schema: 2.0.0
---

# Set-AzureLoadBalancer

## SYNOPSIS
Sets the goal state for a load balancer.

## SYNTAX

```
Set-AzureLoadBalancer -LoadBalancer <PSLoadBalancer> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureLoadBalancer** cmdlet sets the goal state for an Azure load balancer.

## EXAMPLES

### 1:
```

```

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

[Get-AzureLoadBalancer](.\Get-AzureLoadBalancer.md)

[New-AzureLoadBalancer](.\New-AzureLoadBalancer.md)

[Remove-AzureLoadBalancer](.\Remove-AzureLoadBalancer.md)

