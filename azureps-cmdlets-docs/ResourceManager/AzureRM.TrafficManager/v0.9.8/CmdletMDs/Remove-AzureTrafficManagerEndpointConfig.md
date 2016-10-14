---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version: .\Add-AzureTrafficManagerEndpointConfig.md
schema: 2.0.0
---

# Remove-AzureTrafficManagerEndpointConfig

## SYNOPSIS
Removes an endpoint from an Azure Traffic Manager profile.

## SYNTAX

```
Remove-AzureTrafficManagerEndpointConfig -EndpointName <String> -TrafficManagerProfile <TrafficManagerProfile>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureTrafficManagerEndpointConfig** cmdlet removes an endpoint from a local Azure Traffic Manager profile object.
You can get a profile by using the **New-AzureTrafficManagerProfile** or **Get-AzureTrafficManagerProfile** cmdlets.

This cmdlet operates on the local profile object.
Commit your changes to the profile for Traffic Manager by using the **Set-AzureTrafficManagerProfile** cmdlet.

## EXAMPLES

### Example 1: Remove a profile
```
PS C:\>$TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> Remove-AzureTrafficManagerEndpointConfig -EndpointName "contoso" -TrafficManagerProfile $TrafficManagerProfile 
PS C:\> Set-AzureTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

The first command gets an Azure Traffic Manager profile by using the **Get-AzureTrafficManagerProfile** cmdlet.
The command stores the local profile in the $TrafficManagerProfile variable.

The second command removes an endpoint named contoso from the profile stored in $TrafficManagerProfile.
This command changes only the local object.

The final command updates the Traffic Manager profile named ContosoProfile to match the local value in $TrafficManagerProfile.

### Example 2: Remove a profile by using the pipeline
```
PS C:\>Get-AzureTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" | Remove-AzureTrafficManagerEndpointConfig -EndpointName "contoso" | Set-AzureTrafficManagerProfile
```

This command gets a profile, and then passes the local profile to **Remove-AzureTrafficManagerEndpointConfig** by using the pipeline operator.
That cmdlet removes an endpoint named contoso from that profile, and then passes the result to **Set-AzureTrafficManagerProfile**.
The final cmdlet updates the Traffic Manager profile to match the local value.

## PARAMETERS

### -EndpointName
Specifies the name of the Traffic Manager endpoint that this cmdlet removes.

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

### -TrafficManagerProfile
Specifies a local **TrafficManagerProfile** object.
This cmdlet modifies this local object.

```yaml
Type: TrafficManagerProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
You can pipe a **TrafficManagerProfile** object to this cmdlet.

## OUTPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
This cmdlet returns a modified **TrafficManagerProfile** object.

## NOTES

## RELATED LINKS

[Add-AzureTrafficManagerEndpointConfig](.\Add-AzureTrafficManagerEndpointConfig.md)

[Get-AzureTrafficManagerProfile](.\Get-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](.\Set-AzureTrafficManagerProfile.md)

