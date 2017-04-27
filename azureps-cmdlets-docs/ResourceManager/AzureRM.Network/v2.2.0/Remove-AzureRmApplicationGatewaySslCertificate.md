---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmApplicationGatewaySslCertificate

## SYNOPSIS
Removes an SSL certificate from an Azure application gateway.

## SYNTAX

```
Remove-AzureRmApplicationGatewaySslCertificate -Name <String> -ApplicationGateway <PSApplicationGateway>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Remove-AzureRmApplicationGatewaySslCertificate cmdlet removes a Secure Sockets Layer (SSL) certificate from an Azure application gateway.

## EXAMPLES

### --------------------------  Example 1: Remove an SSL certificate from an application gateway  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\>$AppGW = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> Remove-AzureRmApplicationGatewaySslCertificate -ApplicationGateway $AppGW -Name "Cert02"
```

This command removes the SSL certificate named Cert02 from the application gateway named ApplicationGateway01.

## PARAMETERS

### -Name
Specifies the name of an SSL certificate that this cmdlet removes.

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

### -ApplicationGateway
Specifies the application gateway from which this cmdlet removes an SSL certificate.

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

### System.String

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewaySslCertificate]()

[Get-AzureRmApplicationGatewaySslCertificate]()

[New-AzureRmApplicationGatewaySslCertificate]()

[Set-AzureRmApplicationGatewaySslCertificate]()

