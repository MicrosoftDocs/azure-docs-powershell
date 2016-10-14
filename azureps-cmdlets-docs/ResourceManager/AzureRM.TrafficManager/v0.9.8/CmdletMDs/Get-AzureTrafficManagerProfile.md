---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version: .\New-AzureTrafficManagerProfile.md
schema: 2.0.0
---

# Get-AzureTrafficManagerProfile

## SYNOPSIS
Gets an Azure Traffic Manager profile.

## SYNTAX

```
Get-AzureTrafficManagerProfile [-Name <String>] [-ResourceGroupName <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureTrafficManagerProfile** cmdlet gets a Traffic Manager profile from Azure Traffic Manager, and returns an object that represents that profile.
You can modify the local object, and then apply changes to the profile by using the **Set-AzureTrafficManagerProfile** cmdlet.

## EXAMPLES

### Example 1: Get a profile
```
PS C:\>Get-AzureTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
```

This command gets the profile named ContosoProfile in ResourceGroup11.

## PARAMETERS

### -Name
Specifies the name of the Traffic Manager profile to get.

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

### -ResourceGroupName
Specifies the name of a resource group that contains the Traffic Manager profile.```yaml
Type: String
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

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
This cmdlet returns a **TrafficManagerProfile** object.
You can modify this object, and then apply changes to Traffic Manager by using **Set-AzureTrafficManagerProfile**.

## NOTES

## RELATED LINKS

[New-AzureTrafficManagerProfile](.\New-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](.\Remove-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](.\Set-AzureTrafficManagerProfile.md)

