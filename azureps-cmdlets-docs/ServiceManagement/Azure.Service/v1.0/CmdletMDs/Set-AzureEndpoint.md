---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureEndpoint.md
schema: 2.0.0
---

# Set-AzureEndpoint

## SYNOPSIS
Modifies an endpoint assigned to a virtual machine.

## SYNTAX

```
Set-AzureEndpoint [-Name] <String> [[-Protocol] <String>] [[-LocalPort] <Int32>] [-PublicPort <Int32>]
 [-DirectServerReturn <Boolean>] [-ACL <NetworkAclObject>] [-InternalLoadBalancerName <String>]
 [-IdleTimeoutInMinutes <Int32>] [-LoadBalancerDistribution <String>] [-VirtualIPName <String>]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureEndpoint** cmdlet modifies an endpoint assigned to an azure_2 virtual machine.
You can specify changes to an endpoint that is not load balanced.

## EXAMPLES

### Example 1: Modify an endpoint to listen on a port
```
PS C:\>Get-AzureVM -ServiceName "ContosoService" -Name "VirutalMachine01" | Set-AzureEndpoint -Name "Web" -PublicPort 443 -LocalPort 443 -Protocol tcp | Update-AzureVM
```

This command retrieves the configuration of a virtual machine named VirtualMachine01 by using the Get-AzureVM cmdlet.
The command passes it to the current cmdlet by using the pipeline operator.
This cmdlet modifies the endpoint named Web to listen on port 443.
The command passes the virtual machine object to the Update-AzureVM cmdlet, which implements your changes.

## PARAMETERS

### -Name
Specifies the name of the endpoint.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

Required: False
Position: 1
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

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicPort
Specifies the public port that the endpoint uses.

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

### -ACL
Specifies an access control list (ACL) configuration object that this cmdlet applies to the endpoint.

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

### -VirtualIPName
Specifies the name of a virtual IP address that azure_2 associates to the endpoint.
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
ps_azureprofile_description

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
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
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

[Add-AzureEndpoint](.\Add-AzureEndpoint.md)

[Add-AzureVirtualIP](.\Add-AzureVirtualIP.md)

[Get-AzureEndpoint](.\Get-AzureEndpoint.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Remove-AzureEndpoint](.\Remove-AzureEndpoint.md)

[Update-AzureVM](.\Update-AzureVM.md)

