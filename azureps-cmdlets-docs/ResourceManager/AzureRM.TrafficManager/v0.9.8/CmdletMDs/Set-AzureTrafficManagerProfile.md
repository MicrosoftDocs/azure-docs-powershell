---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version: .\Get-AzureTrafficManagerProfile.md
schema: 2.0.0
---

# Set-AzureTrafficManagerProfile

## SYNOPSIS
Updates an Azure Traffic Manager profile.

## SYNTAX

```
Set-AzureTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureTrafficManagerProfile** cmdlet updates an Azure Traffic Manager profile.
This cmdlet updates the settings of the profile from a local profile object.
You can pass a profile object to Traffic Manager by using the pipeline or as a parameter value.

## EXAMPLES

### Example 1: Update a profile
```
PS C:\>$TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> Set-AzureTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

The first command gets an Azure Traffic Manager profile by using the **Get-AzureTrafficManagerProfile** cmdlet.
The command stores the profile locally in the $TrafficManagerProfile variable.
After you get that profile, you can change it locally.

The second command updates the Traffic Manager profile named ContosoProfile to match the local value in $TrafficManagerProfile.

## PARAMETERS

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
You can pipe a **TrafficManagerProfile** object to this cmdlet.

## OUTPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
This cmdlet returns a **TrafficManagerProfile** object.

## NOTES

## RELATED LINKS

[Get-AzureTrafficManagerProfile](.\Get-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](.\New-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](.\Remove-AzureTrafficManagerProfile.md)

