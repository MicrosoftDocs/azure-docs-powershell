---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\New-AzureLoadBalancer.md
schema: 2.0.0
---

# Get-AzureLoadBalancer

## SYNOPSIS
Gets a load balancer.

## SYNTAX

```
Get-AzureLoadBalancer [-Name <String>] [-ResourceGroupName <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureLoadBalancer** cmdlet gets one or more Azure load balancers that are contained in a resource group.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the load balancer to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ResourceGroupName
Specifies the resource group that contains the load balancer to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureLoadBalancer](.\New-AzureLoadBalancer.md)

[Remove-AzureLoadBalancer](.\Remove-AzureLoadBalancer.md)

[Set-AzureLoadBalancer](.\Set-AzureLoadBalancer.md)

