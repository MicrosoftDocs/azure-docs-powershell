---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayBackendHttpSettings.md
schema: 2.0.0
---

# Remove-AzureApplicationGatewayBackendHttpSettings

## SYNOPSIS
Removes back-end HTTP settings from an application gateway.

## SYNTAX

```
Remove-AzureApplicationGatewayBackendHttpSettings -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureApplicationGatewayBackendHttpSettings** cmdlet removes back-end Hypertext Transfer Protocol (HTTP) settings from an Azure application gateway.

## EXAMPLES

### Example 1: Remove back-end HTTP settings from an application gateway
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> Remove-AzureApplicationGatewayBackendHttpSettings -ApplicationGateway $AppGw -Name "BackEndSetting02"
```

The first command gets an application gateway named ApplicationGateway01 that belongs to the resource group named ResourceGroup01 and stores it in the $AppGw variable.

The second command removes the back-end HTTP setting named BackEndSetting02 from the application gateway stored in $AppGw.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway from which this cmdlet removes back-end HTTP settings.

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the back-end HTTP settings that this cmdlet removes.

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
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayBackendHttpSettings](.\Add-AzureApplicationGatewayBackendHttpSettings.md)

[New-AzureApplicationGatewayBackendHttpSettings](.\New-AzureApplicationGatewayBackendHttpSettings.md)

[Get-AzureApplicationGatewayBackendHttpSettings](.\Get-AzureApplicationGatewayBackendHttpSettings.md)

[Set-AzureApplicationGatewayBackendHttpSettings](.\Set-AzureApplicationGatewayBackendHttpSettings.md)

