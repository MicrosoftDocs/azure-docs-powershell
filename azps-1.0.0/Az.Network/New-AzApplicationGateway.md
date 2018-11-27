---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: Az.Network
online version:
schema: 2.0.0
---

# New-AzApplicationGateway

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

```
New-AzApplicationGateway -Name <String> -ResourceGroupName <String> -Location <String>
 -Sku <PSApplicationGatewaySku> [-SslPolicy <PSApplicationGatewaySslPolicy>]
 -GatewayIPConfigurations <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration]>
 [-SslCertificates <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate]>]
 [-AuthenticationCertificates <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAuthenticationCertificate]>]
 [-TrustedRootCertificate <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayTrustedRootCertificate]>]
 [-FrontendIPConfigurations <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration]>]
 -FrontendPorts <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort]>
 [-Probes <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayProbe]>]
 -BackendAddressPools <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool]>
 -BackendHttpSettingsCollection <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings]>
 -HttpListeners <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener]>
 [-UrlPathMaps <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayUrlPathMap]>]
 -RequestRoutingRules <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule]>
 [-RedirectConfigurations <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRedirectConfiguration]>]
 [-WebApplicationFirewallConfiguration <PSApplicationGatewayWebApplicationFirewallConfiguration>]
 [-AutoscaleConfiguration <PSApplicationGatewayAutoscaleConfiguration>] [-EnableHttp2] [-EnableFIPS]
 [-Zone <System.Collections.Generic.List`1[System.String]>] [-Tag <Hashtable>] [-Force] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AsJob
Run cmdlet in the background

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationCertificates
The list of authentication certificates

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAuthenticationCertificate]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoscaleConfiguration
Autoscale Configuration

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAutoscaleConfiguration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendAddressPools
The list of backend address pool

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendHttpSettingsCollection
The list of backend http settings

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFIPS
Whether FIPS is enabled.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableHttp2
Whether HTTP2 is enabled.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Do not ask for confirmation if you want to overrite a resource

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendIPConfigurations
The list of frontend IP config

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FrontendPorts
The list of frontend port

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GatewayIPConfigurations
The list of IPConfiguration (subnet)

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HttpListeners
The list of http listener

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
location.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The resource name.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Probes
The list of probe

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayProbe]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RedirectConfigurations
The list of redirect configuration

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRedirectConfiguration]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequestRoutingRules
The list of request routing rule

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group name.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
The SKU of application gateway

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySku
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SslCertificates
The list of ssl certificates

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SslPolicy
The SSL policy of application gateway

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
A hashtable which represents resource tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TrustedRootCertificate
The list of trusted root certificates

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayTrustedRootCertificate]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UrlPathMaps
The list of UrlPathMap

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayUrlPathMap]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WebApplicationFirewallConfiguration
Firewall configuration

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayWebApplicationFirewallConfiguration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
A list of availability zones denoting where the application gateway needs to come from.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySku

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslPolicy

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAuthenticationCertificate, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayTrustedRootCertificate, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayProbe, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayUrlPathMap, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRedirectConfiguration, Microsoft.Azure.Commands.Network, Version=6.9.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayWebApplicationFirewallConfiguration

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAutoscaleConfiguration

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS
