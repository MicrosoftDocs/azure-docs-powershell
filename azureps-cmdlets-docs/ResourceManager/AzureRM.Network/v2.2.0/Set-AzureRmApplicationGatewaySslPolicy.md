---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmApplicationGatewaySslPolicy

## SYNOPSIS
Modifies the Ssl policy of an application gateway.

## SYNTAX

```
Set-AzureRmApplicationGatewaySslPolicy -ApplicationGateway <PSApplicationGateway>
 -DisabledSslProtocols <System.Collections.Generic.List`1[System.String]>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The Set-AzureRmApplicationGatewaySslPolicy cmdlet modifies the Ssl policy of an application gateway.

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ApplicationGateway
@{Text=}

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

### -DisabledSslProtocols
@{Text=}

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}

```yaml
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
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
@{Text=}

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

### -Confirm
@{Text=}

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

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

