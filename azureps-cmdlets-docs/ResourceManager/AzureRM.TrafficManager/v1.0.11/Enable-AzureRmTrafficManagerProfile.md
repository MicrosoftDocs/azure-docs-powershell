---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version:
schema: 2.0.0
---

# Enable-AzureRmTrafficManagerProfile

## SYNOPSIS
Enables an Azure Traffic Manager profile.

## SYNTAX

### Fields
```
Enable-AzureRmTrafficManagerProfile -Name <String> -ResourceGroupName <String> [<CommonParameters>]
```

### Object
```
Enable-AzureRmTrafficManagerProfile -TrafficManagerProfile <TrafficManagerProfile> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-AzureRmTrafficManagerProfile** cmdlet enables an Azure Traffic Manager profile.

You can use the pipeline operator to pass a **TrafficManagerProfile** object to this cmdlet or you can pass a **TrafficManagerProfile** object in the *TrafficManagerProfile* parameter.
Alternatively, you can specify the profile by using the *Name* and *ResourceGroupName* parameters.

## EXAMPLES

### Example 1: Enable a profile specified by name
```
PS C:\> Enable-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
```

This command enables the profile named "ContosoProfile" in the "ResourceGroup11" resource group.

### Example 2: Enable a profile by using the pipeline
```
PS C:\> Get-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11" | Enable-AzureRmTrafficManagerProfile
```

This command gets the specified profile and then passes that profile to the **Enable-AzureRmTrafficManagerProfile** cmdlet by using the pipeline operator.

## PARAMETERS

### -Name
Specifies the name of the profile to be enabled.

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
Specifies the name of the resource group that contains the profile.

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
Specifies a **TrafficManagerProfile** object that contains details about the profile to be enabled.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Disable-AzureRmTrafficManagerProfile](./Disable-AzureRmTrafficManagerProfile.md)

[Get-AzureRmTrafficManagerProfile](./Get-AzureRmTrafficManagerProfile.md)

[New-AzureRmTrafficManagerProfile](./New-AzureRmTrafficManagerProfile.md)

[Remove-AzureRmTrafficManagerProfile](./Remove-AzureRmTrafficManagerProfile.md)

[Set-AzureRmTrafficManagerProfile](./Set-AzureRmTrafficManagerProfile.md)
