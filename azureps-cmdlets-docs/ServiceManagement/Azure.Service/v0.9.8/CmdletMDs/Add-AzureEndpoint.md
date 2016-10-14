---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureVirtualIP.md
schema: 2.0.0
---

# Add-AzureEndpoint

## SYNOPSIS
Adds an endpoint to a virtual machine.

## SYNTAX

### NoLB (Default)
```
Add-AzureEndpoint [-Name] <String> [-Protocol] <String> [-LocalPort] <Int32> [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] [-InternalLoadBalancerName <String>]
 [-IdleTimeoutInMinutes <Int32>] [-LoadBalancerDistribution <String>] [-VirtualIPName <String>]
 -VM <IPersistentVM> [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

### LBCustomProbe
```
Add-AzureEndpoint [-Name] <String> [-Protocol] <String> [-LocalPort] <Int32> [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] -LBSetName <String> -ProbePort <Int32>
 -ProbeProtocol <String> [-ProbePath <String>] [-ProbeIntervalInSeconds <Int32>]
 [-ProbeTimeoutInSeconds <Int32>] [-InternalLoadBalancerName <String>] [-IdleTimeoutInMinutes <Int32>]
 [-LoadBalancerDistribution <String>] [-VirtualIPName <String>] -VM <IPersistentVM> [-Profile <AzureProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### LBNoProbe
```
Add-AzureEndpoint [-Name] <String> [-Protocol] <String> [-LocalPort] <Int32> [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] -LBSetName <String> [-NoProbe]
 [-InternalLoadBalancerName <String>] [-IdleTimeoutInMinutes <Int32>] [-LoadBalancerDistribution <String>]
 [-VirtualIPName <String>] -VM <IPersistentVM> [-Profile <AzureProfile>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

### LBDefaultProbe
```
Add-AzureEndpoint [-Name] <String> [-Protocol] <String> [-LocalPort] <Int32> [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] -LBSetName <String> [-DefaultProbe]
 [-InternalLoadBalancerName <String>] [-IdleTimeoutInMinutes <Int32>] [-LoadBalancerDistribution <String>]
 [-VirtualIPName <String>] -VM <IPersistentVM> [-Profile <AzureProfile>] [-PipelineVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureEndpoint** cmdlet adds an endpoint to an Azure virtual machine object.

## EXAMPLES

### Example 1: Add an endpoint
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "VirutalMachine01" | Add-AzureEndpoint -Name "HttpIn" -Protocol "tcp" -PublicPort 80 -LocalPort 8080 | Update-AzureVM
```

This command retrieves the configuration of a virtual machine named VirtualMachine01 by using the Get-AzureVM cmdlet.
The command passes it to the current cmdlet by using the pipeline operator.
This cmdlet adds an endpoint named HttpIn.
The endpoint has a public port 80 and local port 8080.
The command passes the virtual machine object to the Update-AzureVM cmdlet, which implements your changes.

### Example 2: Add an endpoint that belongs to a load balanced group
```
PS C:\>Get-AzureVM -ServiceName "LoadBalancedService" -Name "VirtualMachine12" | Add-AzureEndpoint -Name "HttpIn" -Protocol "tcp" -PublicPort 80 -LocalPort 8080 -LBSetName "WebFarm" -ProbePort 80 -ProbeProtocol "http" -ProbePath '/' | Update-AzureVM
```

This command retrieves the configuration of a virtual machine named VirtualMachine07.
The current cmdlet adds an endpoint named HttpIn.
The endpoint has a public port 80 and local port 8080.
The endpoint belongs to the shared load balanced group named WebFarm.
An HTTP probe on port 80 with a path of '/' monitors the availability of the endpoint.
The command implements your changes.

### Example 3: Associate a virtual IP to an endpoint
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine25" | Add-AzureEndpoint -Name "HttpIn" -Protocol "tcp" -LocalPort 8080 -PublicPort 80 -VirtualIPName "ContosoVip11" | Update-AzureVM
```

This command retrieves the configuration of a virtual machine named VirtualMachine25.
The current cmdlet adds an endpoint named HttpIn.
The endpoint has a public port 80 and local port 8080.
This command associates a virtual IP to the endpoint.
The command implements your changes.

## PARAMETERS

### -ACL
Specifies an access control list (ACL) configuration object for the endpoint.

```yaml
Type: NetworkAclObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProbe
Indicates that this cmdlet uses the default probe setting.

```yaml
Type: SwitchParameter
Parameter Sets: LBDefaultProbe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectServerReturn
Specifies whether this cmdlet enables direct server return.
Specify $True to enable, or $False to disable.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeoutInMinutes
Specifies the TCP idle time-out period, in minutes, for the endpoint.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalLoadBalancerName
Specifies the name of the internal load balancer.

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

### -LBSetName
Specifies the name of the load balancer set for the endpoint.

```yaml
Type: String
Parameter Sets: LBCustomProbe, LBNoProbe, LBDefaultProbe
Aliases: LoadBalancedEndpointSetName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerDistribution
Specifies the load balancer distribution algorithm.
Valid values are: 

- sourceIP.
A two tuple affinity: Source IP, Destination IP 
- sourceIPProtocol.
A three tuple affinity: Source IP, Destination IP, Protocol 
- none.
A five tuple affinity: Source IP, Source Port, Destination IP, Destination Port, Protocol 

The default value is none.

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

### -LocalPort
Specifies the local, private, port that this endpoint uses.
Applications within the virtual machine listen on this port for service input requests for this endpoint.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the endpoint.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoProbe
Indicates that this cmdlet uses the no probe setting.

```yaml
Type: SwitchParameter
Parameter Sets: LBNoProbe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Not Specified```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeIntervalInSeconds
Specifies the probe polling interval, in seconds, for the endpoint.

```yaml
Type: Int32
Parameter Sets: LBCustomProbe
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbePath
Specifies the relative path to the HTTP probe.

```yaml
Type: String
Parameter Sets: LBCustomProbe
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbePort
Specifies the port that the endpoint uses.

```yaml
Type: Int32
Parameter Sets: LBCustomProbe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeProtocol
Specifies the port protocol.
Valid values are: 

- tcp 
- http

```yaml
Type: String
Parameter Sets: LBCustomProbe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProbeTimeoutInSeconds
Specifies the probe polling time-out period in seconds.

```yaml
Type: Int32
Parameter Sets: LBCustomProbe
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol of the endpoint.
Valid values are: 

- tcp 
- udp

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicPort
Specifies the public port that the endpoint uses.
If you do not specify a value, Azure assigns an available port.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualIPName
Specifies the name of a virtual IP address that Azure associates to the endpoint.
Your service can have multiple virtual IPs.
To create virtual IPs, use the Add-AzureVirtualIP cmdlet.

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

### -VM
Specifies the virtual machine to which the endpoint belongs.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### System.Object

## NOTES

## RELATED LINKS

[Add-AzureVirtualIP](.\Add-AzureVirtualIP.md)

[Get-AzureEndpoint](.\Get-AzureEndpoint.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Remove-AzureEndpoint](.\Remove-AzureEndpoint.md)

[Set-AzureEndpoint](.\Set-AzureEndpoint.md)

[Update-AzureVM](.\Update-AzureVM.md)

