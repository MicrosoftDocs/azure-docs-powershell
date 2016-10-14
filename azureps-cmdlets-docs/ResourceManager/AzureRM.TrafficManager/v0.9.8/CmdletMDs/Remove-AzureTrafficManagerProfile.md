---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version: .\Get-AzureTrafficManagerProfile.md
schema: 2.0.0
---

# Remove-AzureTrafficManagerProfile

## SYNOPSIS
Deletes an Azure Traffic Manager profile.

## SYNTAX

### Fields
```
Remove-AzureTrafficManagerProfile -Name <String> -ResourceGroupName <String> [-Force] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### Object
```
Remove-AzureTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile> [-Force]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureTrafficManagerProfile** cmdlet deletes an Azure Traffic Manager profile.
You can specify a profile to delete by name, or you can specify a profile object.
You can delete a profile object from Traffic Manager by using the pipeline or as a parameter value.

## EXAMPLES

### Example 1: Delete a profile specified by name
```
PS C:\>Remove-AzureTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
```

This command deletes the profile named ContosoProfile in ResourceGroup11.

### Example 2: Delete a profile by using the pipeline
```
PS C:\>Get-AzureTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" | Remove-AzureTrafficManagerProfile
```

This command gets the profile named ContosoProfile in ResourceGroup11, and then passes that profile to the current cmdlet by using the pipeline operator.
The current command deletes that profile.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the Traffic Manager profile that this cmdlet deletes.

```yaml
Type: String
Parameter Sets: Fields
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

### -ResourceGroupName
Specifies the name of a resource group. This cmdlet deletes a Traffic Manager profile in the group that this parameter specifies.```yaml
Type: String
Parameter Sets: Fields
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficManagerProfile
Specifies a TrafficManagerProfile object to delete.```yaml
Type: TrafficManagerProfile
Parameter Sets: Object
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

### Boolean
This cmdlet returns a value of $True, if it succeeds or, if the deletion fails, a value of $False.

## NOTES

## RELATED LINKS

[Get-AzureTrafficManagerProfile](.\Get-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](.\New-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](.\Set-AzureTrafficManagerProfile.md)

