---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmLoadBalancerProbeConfig

## SYNOPSIS
Creates a probe configuration for a load balancer.

## SYNTAX

```
New-AzureRmLoadBalancerProbeConfig -Name <String> [-RequestPath <String>] [-Protocol <String>] -Port <Int32>
 -IntervalInSeconds <Int32> -ProbeCount <Int32> [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmLoadBalancerProbeConfig cmdlet creates a probe configuration for an Azure load balancer.
A probe enables one to keep track of the health of virtual machines.
Probes enable automatic removal of those virtual machines that fail the health check.

## EXAMPLES

### --------------------------  Example 1  Creating a new probe  --------------------------
@{paragraph=PS C:\\\>}





```
New-AzureRmLoadBalancerProbeConfig -Name MyProbe -Protocol http -Port 80 -IntervalInSeconds 15 -ProbeCount 15
```

This command creates a new Probe configuration called MyProbe using http protocol.
In this case port 80 will be the port on which this new probe will connect to a load balanced service.
IntervalInSeconds is 15 and ProbeCount is 15.

Name               : MyProbe
Id                 : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/ResourceGroupNotSet/providers/Microsoft.Network/loadBalancers/LoadBalancerNameNotSet/probes/MyProbe
Etag               :
ProvisioningState  :
Protocol           : http
Port               : 80
IntervalInSeconds  : 15
NumberOfProbes     : 15
RequestPath        :
LoadBalancingRules : null

## PARAMETERS

### -Name
Specifies the name of the probe configuration to create.

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

### -RequestPath
Specifies the path in a load-balanced service to probe to determine health.

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

### -Protocol
Specifies the protocol to use for the probe configuration.
The acceptable values for this parameter are:Tcp or Http.

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

### -Port
Specifies the port on which the new probe should connect to a load-balanced service.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntervalInSeconds
Specifies the interval, in seconds, between probes to each instance of a load-balanced service.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeCount
Specifies the number of per-instance consecutive failures for an instance to be considered unhealthy.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
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

[Add-AzureRmLoadBalancerProbeConfig]()

[Get-AzureRmLoadBalancerProbeConfig]()

[Remove-AzureRmLoadBalancerProbeConfig]()

[Set-AzureRmLoadBalancerProbeConfig]()

