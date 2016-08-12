---
external help file: RMAzure_Apimanagement.xml
online version: 2a7ef835-586c-4e86-a243-3cc0e9623d71
schema: 2.0.0
---

# Set-AzureRmApiManagementHostnames
## SYNOPSIS
Sets a custom hostname configuration for an API Management service proxy or portal.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-AzureRmApiManagementHostnames [-PassThru] -ApiManagement <PsApiManagement>
```

### UNNAMED_PARAMETER_SET_2
```
Set-AzureRmApiManagementHostnames [-PassThru]
 [-PortalHostnameConfiguration <PsApiManagementHostnameConfiguration>]
 [-ProxyHostnameConfiguration <PsApiManagementHostnameConfiguration>] -Name <String>
 -ResourceGroupName <String>
```

## DESCRIPTION
The **Set-AzureRmApiManagementHostnames** cmdlet applies a custom hostname configuration for an API Management service proxy or portal.

## EXAMPLES

### Example 1: Set the custom hostname configuration for a proxy and portal
```
PS C:\>Set-AzureRmApiManagementHostnames -Name ContosoApi -ResourceGroupName Contoso -PortalHostnameConfiguration $portalHostnameConf -ProxyHostnameConfiguration $proxyHostnameConf
```

This command sets the custom hostname configuration for proxy and portal.

### Example 2: Configure a custom hostname for a proxy and portal
```
PS C:\>Import-AzureRmApiManagementHostnameCertificate -Name ContosoApi -ResourceGroupName "Contoso" -HostnameType "Proxy" -PfxPath "C:\proxycert.pfx" -PfxPassword "CertSecret"
PS C:\> Import-AzureRmApiManagementHostnameCertificate -Name "ContosoApi" -ResourceGroupName "Contoso" -HostnameType "Portal" -PfxPath "C:\portalcert.pfx" -PfxPassword "CertSecret"
PS C:\> $PortalHostnameConf = New-AzureRmApiManagementHostnameConfiguration -Hostname "portal.contoso.com" -CertificateThumbprint "33CC47C6FCA848DC9B14A6F071C1EF7C"
PS C:\> $ProxyHostnameConf = New-AzureRmApiManagementHostnameConfiguration -Hostname "proxy.contoso.com" -CertificateThumbprint "5DD7CCF6A1E74E0987DD2873406B7264"
PS C:\> Set-AzureRmApiManagementHostnames -Name "ContosoApi" -ResourceGroupName "Contoso" -PortalHostnameConfiguration $PortalHostnameConf -ProxyHostnameConfiguration $ProxyHostnameConf
```

This example configures a custom hostname for proxy and portal.
You need to import corresponding certificates and then apply the custom hostnames.

## PARAMETERS

### -ApiManagement
Specifies the **PsApiManagement** instance that this cmdlet gets the *PortalHostnameConfiguration* and *ProxyHostnameConfiguration* parameters from.

```yaml
Type: PsApiManagement
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the API Management instance.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
passthru

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

### -PortalHostnameConfiguration
Specifies the custom portal hostname configuration.
Passing $null to the cmdlet sets the default hostname.

```yaml
Type: PsApiManagementHostnameConfiguration
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ProxyHostnameConfiguration
Specifies the custom proxy hostname configuration.
Passing $null sets the default hostname.

```yaml
Type: PsApiManagementHostnameConfiguration
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group under which the API Management instance exists.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Import-AzureRmApiManagementHostnameCertificate](2a7ef835-586c-4e86-a243-3cc0e9623d71)

[New-AzureRmApiManagementHostnameConfiguration](73f73a6f-470c-4dd6-95c4-a1302fabb0dd)

