---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmTrafficManagerProfile

## SYNOPSIS
Deletes an Azure Traffic Manager profile.

## SYNTAX

### Fields
```
Remove-AzureRmTrafficManagerProfile -Name <String> -ResourceGroupName <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Object
```
Remove-AzureRmTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile> [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Remove-AzureRmTrafficManagerProfile cmdlet deletes an Azure Traffic Manager profile.
You can specify a profile to delete by name, or you can specify a profile object.
You can delete a profile object from Traffic Manager by using the pipeline or as a parameter value.

## EXAMPLES

### Example 1: Delete a profile specified by name
```
PS C:\>Remove-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
```

This command deletes the profile named ContosoProfile in ResourceGroup11.

### Example 2: Delete a profile by using the pipeline
```
PS C:\>Get-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" | Remove-AzureRmTrafficManagerProfile
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

### -ResourceGroupName
Specifies the name of a resource group.
This cmdlet deletes a Traffic Manager profile in the group that this parameter specifies.

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

### -TrafficManagerProfile
Specifies a TrafficManagerProfile object to delete.

```yaml
Type: TrafficManagerProfile
Parameter Sets: Object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
You can pipe a TrafficManagerProfile object to this cmdlet.

## OUTPUTS

### Boolean
This cmdlet returns a value of $True, if it succeeds or, if the deletion fails, a value of $False.

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, traffic, trafficmanager

## RELATED LINKS

[Get-AzureRmTrafficManagerProfile]()

[New-AzureRmTrafficManagerProfile]()

[Set-AzureRmTrafficManagerProfile]()

