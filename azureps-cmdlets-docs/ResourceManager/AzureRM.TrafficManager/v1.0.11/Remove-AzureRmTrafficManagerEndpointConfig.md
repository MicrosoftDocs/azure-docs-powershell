---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-AzureRmTrafficManagerEndpointConfig

## SYNOPSIS
Removes an endpoint from an Azure Traffic Manager profile.

## SYNTAX

```
Remove-AzureRmTrafficManagerEndpointConfig -EndpointName <String>
 -TrafficManagerProfile <TrafficManagerProfile> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmTrafficManagerEndpointConfig** cmdlet removes an endpoint from an Azure Traffic Manager profile.

This cmdlet operates on the local profile object.
Commit your changes to the profile for Traffic Manager by using the **Set-AzureRmTrafficManagerProfile** cmdlet.
You can get a profile object by using the **New-AzureRmTrafficManagerProfile** cmdlet or the **Get-AzureRmTrafficManagerProfile** cmdlet.

## EXAMPLES

### Example 1: Remove an endpoint from the specified profile
```
PS C:\> $TrafficManagerProfile = Get-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> Remove-AzureRmTrafficManagerEndpointConfig -EndpointName "contoso" -TrafficManagerProfile $TrafficManagerProfile
PS C:\> Set-AzureRmTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

The first command gets the profile named "ContosoProfile" in the resource group named "ResourceGroup11" and stores the profile object in the *$TrafficManagerProfile* variable.
The profile object is then passed in the *TrafficManagerProfile* parameter of the **Remove-AzureRmTrafficManagerEndpointConfig** cmdlet, which changes only the local profile object.
The **Set-AzureRmTrafficManagerProfile** cmdlet updates the Traffic Manager profile named "ContosoProfile" to match the local value in *$TrafficManagerProfile*.

### Example 2: Remove an endpoint by using the pipeline
```
PS C:\> Get-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" | Remove-AzureRmTrafficManagerEndpointConfig -EndpointName "contoso" | Set-AzureRmTrafficManagerProfile
```

This command gets the specified profile and then passes the profile to the **Remove-AzureRmTrafficManagerEndpointConfig** cmdlet by using the pipeline operator.
The updated local profile, which is output by the **Remove-AzureRmTrafficManagerEndpointConfig** cmdlet, is finally passed to **Set-AzureRmTrafficManagerProfile** by using the pipeline operator.

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

### -TrafficManagerProfile
Specifies a **TrafficManagerProfile** object that contains details about the profile.
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
Keywords: azure, azurerm, arm, resource, management, manager, traffic, trafficmanager

## RELATED LINKS

[Add-AzureRmTrafficManagerEndpointConfig](./Add-AzureRmTrafficManagerEndpointConfig.md)

[Get-AzureRmTrafficManagerProfile](./Get-AzureRmTrafficManagerProfile.md)

[New-AzureRmTrafficManagerProfile](./New-AzureRmTrafficManagerProfile.md)

[Remove-AzureRmTrafficManagerEndpoint](./Remove-AzureRmTrafficManagerEndpoint.md)

[Set-AzureRmTrafficManagerProfile](./Set-AzureRmTrafficManagerProfile.md)
