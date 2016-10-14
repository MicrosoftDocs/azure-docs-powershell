---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=398289
schema: 2.0.0
---

# Set-AzureTrafficManagerProfile

## SYNOPSIS
Updates the properties of a Traffic Manager profile.

## SYNTAX

```
Set-AzureTrafficManagerProfile [-Name <String>] [-LoadBalancingMethod <String>] [-MonitorPort <Int32>]
 [-MonitorProtocol <String>] [-MonitorRelativePath <String>] [-Ttl <Int32>]
 [-TrafficManagerProfile] <IProfileWithDefinition> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureTrafficManagerProfile** cmdlet updates the properties of a Microsoft Azure Traffic Manager profile.

For profiles for which you have set the *LoadBalancingMethod* value to "Failover", you can determine the failover order of the endpoints you have added to your profile with the Add-AzureTrafficManagerEndpoint cmdlet.
For more information, see Example 3 below.

## EXAMPLES

### Example 1: Set the TTL for a Traffic Manager profile
```
PS C:\>Set-AzureTrafficManagerProfile -TrafficManagerProfile $MyTrafficManagerProfile -Ttl 60
```

This command sets the TTL to 60 seconds for the Traffic Manager profile object MyTrafficManagerProfile.

### Example 2: Set several values for a profile
```
PS C:\>Get-AzureTrafficManagerProfile -Name "MyProfile" | Set-AzureTrafficManagerProfile -LoadBalancingMethod "RoundRobin" -Ttl 30 -MonitorProtocol "Http" -MonitorPort 80 -MonitorRelativePath "/"
```

This command gets a Traffic Manager profile named MyProfile by using the **Get-AzureTrafficManagerProfile** cmdlet.
The profile uses the RoundRobin load balancing method, a TTL of 30 seconds,  the monitor protocol HTTP, the monitor port, and the relative path for a Traffic Manager profile.

### Example 3: Reorder endpoints to desired failover order
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
Specifies the name of the Traffic Manager profile to update.

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

Required: False
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

Required: False
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

Required: False
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ttl
Specifies the DNS Time-to-Live (TTL) that informs the Local DNS resolvers how long to cache DNS entries.
Valid values are an integer from 30 through 999,999.

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

### -TrafficManagerProfile
Specifies the Traffic Manager profile object you use to set the profile.

```yaml
Type: IProfileWithDefinition
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[New-AzureTrafficManagerProfile](.\New-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](.\Remove-AzureTrafficManagerProfile.md)

