---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\New-AzureRmApplicationGatewaySslPolicy.md
schema: 2.0.0
---

# Get-AzureRmApplicationGatewaySslPolicy

## SYNOPSIS
Gets the SSL policy of an application gateway.

## SYNTAX

```
Get-AzureRmApplicationGatewaySslPolicy -ApplicationGateway <PSApplicationGateway>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApplicationGatewaySslPolicy** cmdlet gets the SSL policy of an application gateway.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway of the SSL policy that this cmdlet gets.

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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslPolicy

## NOTES
* Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[New-AzureRmApplicationGatewaySslPolicy](.\New-AzureRmApplicationGatewaySslPolicy.md)

[Set-AzureRmApplicationGatewaySslPolicy](.\Set-AzureRmApplicationGatewaySslPolicy.md)

