---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayFrontendPort.md
schema: 2.0.0
---

# Remove-AzureApplicationGatewayFrontendPort

## SYNOPSIS
Removes a front-end port from an application gateway.

## SYNTAX

```
Remove-AzureApplicationGatewayFrontendPort -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureApplicationGatewayFrontendPort** cmdlet removes a front-end port from an Azure application gateway.

## EXAMPLES

### Example: Remove a front-end port from an application gateway
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> Remove-AzureApplicationGatewayFrontendPort -ApplicationGateway $ AppGw -Name "FrontEndPort02"
```

The first command gets an application gateway named ApplicationGateway01 that belongs to the resource group named ResourceGroup01 and stores the gateway in $AppGw variable.

The second command removes the port named FrontEndPort02 from the application gateway.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway from which to remove a front-end port.

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
Specifies name of the frontend port to remove.

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

[Add-AzureApplicationGatewayFrontendPort](.\Add-AzureApplicationGatewayFrontendPort.md)

[Get-AzureApplicationGatewayFrontendPort](.\Get-AzureApplicationGatewayFrontendPort.md)

[New-AzureApplicationGatewayFrontendPort](.\New-AzureApplicationGatewayFrontendPort.md)

[Set-AzureApplicationGatewayFrontendPort](.\Set-AzureApplicationGatewayFrontendPort.md)

