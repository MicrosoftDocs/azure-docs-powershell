---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=398284
schema: 2.0.0
---

# Get-AzureTrafficManagerProfile

## SYNOPSIS
Gets the details of a Traffic Manager profile.

## SYNTAX

```
Get-AzureTrafficManagerProfile [[-Name] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureTrafficManagerProfile** cmdlet gets the details of a Microsoft Azure Traffic Manager profile.
If you do not specify the *Name* parameter, the cmdlet lists the Traffic Manager profiles in the current subscription.

## EXAMPLES

### Example 1: Get the list of Traffic Manager profiles in a subscription
```
PS C:\>Get-AzureTrafficManagerProfile
```

This command gets the list of Traffic Manager profiles in your subscription.

### Example 2: Get a Traffic Manager profile
```
PS C:\>Get-AzureTrafficManagerProfile -Name "MyProfile"
```

This command gets the Traffic Manager profile named MyProfile.

### Example 3: Add an endpoint to a Traffic Manager profile
```
PS C:\>Get-AzureTrafficManagerProfile -Name "MyProfile" | Add-AzureTrafficManagerEndpoint -DomainName "Myapp2.cloudapp.net" -TrafficManagerProfile $MyTrafficManagerProfile -Type "CloudService" -Status "Enabled" | Set-AzureTrafficManagerProfile
```

This command adds an endpoint to a Traffic Manager profile, and then saves the profile.

## PARAMETERS

### -Name
Specifies the name of the Traffic Manager profile to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
@{Text=}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
This cmdlet generates a Traffic Manager profile object or objects.

## NOTES

## RELATED LINKS

[Add-AzureTrafficManagerEndpoint](.\Add-AzureTrafficManagerEndpoint.md)

[Disable-AzureTrafficManagerProfile](.\Disable-AzureTrafficManagerProfile.md)

[Enable-AzureTrafficManagerProfile](.\Enable-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](.\New-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](.\Remove-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](.\Set-AzureTrafficManagerProfile.md)

