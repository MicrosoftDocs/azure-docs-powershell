---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=398285
schema: 2.0.0
---

# New-AzureTrafficManagerProfile

## SYNOPSIS
Creates a Traffic Manager profile.

## SYNTAX

```
New-AzureTrafficManagerProfile [-Name] <String> [-DomainName] <String> -LoadBalancingMethod <String>
 -MonitorPort <Int32> -MonitorProtocol <String> -MonitorRelativePath <String> -Ttl <Int32>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureTrafficManagerProfile** cmdlet creates a Microsoft Azure Traffic Manager profile.

After you create a profile where you set the *LoadBalancingMethod* value to "Failover", you can determine the failover order of the endpoints you add to your profile with the Add-AzureTrafficManagerEndpoint cmdlet.
For more information, see Example 2 below.

## EXAMPLES

### Example 1: Create a Traffic Manager profile
```
PS C:\>New-AzureTrafficManagerProfile -Name "MyProfile" -DomainName "My.profile.trafficmanager.net" -LoadBalancingMethod "RoundRobin" -Ttl 30 -MonitorProtocol "Http" -MonitorPort 80 -MonitorRelativePath "/"
```

This command creates a Traffic Manager profile named MyProfile in the specified Traffic Manager domain with a Round Robin load balancing method, a TTL of 30 seconds, HTTP monitoring protocol, monitoring port 80, and with the specified path.

### Example 2: Reorder endpoints to desired failover order
```
PS C:\>$Profile = Get-AzureTrafficManagerProfile -Name "MyProfile"
PS C:\> $Profile.Endpoints[0],$Profile.Endpoints[1] = $Profile.Endpoints[1],$Profile.Endpoints[0]
PS C:\> $Profile = Set-AzureTrafficManagerProfile
```

This example reorders the endpoints added to MyProfile to the desired failover order.

The first command gets the Traffic Manager profile object named MyProfile and stores the object in the $Profile variable.

The second command re-orders the endpoints from  the endpoints array to the order in which failover should occur.

The last command updates the Traffic Manager profile stored in $Profile with the new endpoint order.

## PARAMETERS

### -Name
Specifies the name of the Traffic Manager profile to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DomainName
Specifies the domain name of the Traffic Manager profile.
This must be a subdomain of trafficmanager.net.

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

### -LoadBalancingMethod
Specifies the load balancing method to use to distribute the connection.
Valid values are: 

- Performance
- Failover
- RoundRobin

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

### -MonitorPort
Specifies the port used to monitor endpoint health.
Valid values are integer values greater than 0 and less than or equal to 65,535.

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

### -MonitorProtocol
Specifies the protocol to use to monitor endpoint health.
Valid values are: 

- Http

- Https

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

### -MonitorRelativePath
Specifies the path relative to the endpoint domain name to probe for health state.
The path must meet the following restrictions: 

- The path must be from 1 through 1000 characters.

- It must start with a forward slash, /.

- It must contain no XML elements, \<\>.

- It must contain no double slashes, //.

- It must contain no invalid HTML escape characters.
For example, %XY.

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

### -Ttl
Specifies the DNS Time-to-Live (TTL) that informs the Local DNS resolvers how long to cache DNS entries.
Valid values are integers from 30 through 999,999.

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

### -Profile
In-memory profile.```yaml
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

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
This cmdlet generates a Traffic Manager profile object.

## NOTES

## RELATED LINKS

[Disable-AzureTrafficManagerProfile](.\Disable-AzureTrafficManagerProfile.md)

[Enable-AzureTrafficManagerProfile](.\Enable-AzureTrafficManagerProfile.md)

[Get-AzureTrafficManagerProfile](.\Get-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](.\Remove-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](.\Set-AzureTrafficManagerProfile.md)

