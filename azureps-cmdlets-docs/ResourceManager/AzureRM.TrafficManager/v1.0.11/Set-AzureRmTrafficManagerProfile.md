---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmTrafficManagerProfile

## SYNOPSIS
Updates an Azure Traffic Manager profile.

## SYNTAX

```
Set-AzureRmTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile> [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureRmTrafficManagerProfile cmdlet updates an Azure Traffic Manager profile.
This cmdlet updates the settings of the profile from a local profile object.
You can pass a profile object to Traffic Manager by using the pipeline or as a parameter value.

## EXAMPLES

### Example 1: Update a profile
```
PS C:\>$TrafficManagerProfile = Get-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> Set-AzureRmTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

The first command gets an Azure Traffic Manager profile by using the Get-AzureRmTrafficManagerProfile cmdlet.
The command stores the profile locally in the $TrafficManagerProfile variable.
After you get that profile, you can change it locally.

The second command updates the Traffic Manager profile named ContosoProfile to match the local value in $TrafficManagerProfile.

## PARAMETERS

### -TrafficManagerProfile
Specifies a local TrafficManagerProfile object.
This cmdlet updates  Traffic Manager to match this local object.

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
You can pipe a TrafficManagerProfile object to this cmdlet.

## OUTPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
This cmdlet returns a TrafficManagerProfile object.

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, traffic, trafficmanager

## RELATED LINKS

[Get-AzureRmTrafficManagerProfile]()

[New-AzureRmTrafficManagerProfile]()

[Remove-AzureRmTrafficManagerProfile]()

