---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmApplicationGateway

## SYNOPSIS
Updates an application gateway.

## SYNTAX

```
Set-AzureRmApplicationGateway -ApplicationGateway <PSApplicationGateway>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Set-AzureRmApplicationGateway cmdlet updates an Azure application gateway.

## EXAMPLES

### --------------------------  Example 1: Update an application gateway  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $UpdatedAppGw = Set-AzureRmApplicationGateway -ApplicationGateway $AppGw
```

This command updates the application gateway with settings in the $AppGw variable and stores the updated gateway in the $UpdatedAppGw variable.

## PARAMETERS

### -ApplicationGateway
Specifies an application gateway object representing the state to which the application gateway should be set.

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

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Start-AzureRmApplicationGateway]()

