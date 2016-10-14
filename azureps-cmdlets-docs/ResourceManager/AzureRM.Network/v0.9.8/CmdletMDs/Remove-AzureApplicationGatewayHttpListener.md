---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayHttpListener.md
schema: 2.0.0
---

# Remove-AzureApplicationGatewayHttpListener

## SYNOPSIS
Removes an HTTP listener from an application gateway.

## SYNTAX

```
Remove-AzureApplicationGatewayHttpListener -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureApplicationGatewayHttpListener** cmdlet removes an HTTP listener from an Azureapplication gateway.

## EXAMPLES

### 1:
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> Remove-AzureApplicationGatewayHttpListener -ApplicationGateway $AppGw -Name "Listener02"
```

The first command gets an application gateway and stores it in the $AppGw variable.

The second command removes the HTTP listener named Listener02 from the application gateway stored in $AppGw.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway from which to remove an HTTP listener.

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
Specifies the name of the HTTP listener to remove.

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

[Add-AzureApplicationGatewayHttpListener](.\Add-AzureApplicationGatewayHttpListener.md)

[Get-AzureApplicationGatewayHttpListener](.\Get-AzureApplicationGatewayHttpListener.md)

[New-AzureApplicationGatewayHttpListener](.\New-AzureApplicationGatewayHttpListener.md)

[Set-AzureApplicationGatewayHttpListener](.\Set-AzureApplicationGatewayHttpListener.md)

