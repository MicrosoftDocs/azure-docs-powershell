---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmWebAppSSLBinding

## SYNOPSIS
Gets a secure sockets layer (SSL) binding for a web app.

## SYNTAX

### S1
```
Get-AzureRmWebAppSSLBinding [[-Name] <String>] [-ResourceGroupName] <String> [-WebAppName] <String>
 [[-Slot] <String>] [<CommonParameters>]
```

### S2
```
Get-AzureRmWebAppSSLBinding [[-Name] <String>] [-WebApp] <Site> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmWebAppSSLBinding** cmdlet gets a secure sockets layer (SSL) binding for a web app that was built using the Web Apps feature of the Azure App Service.

SSL bindings are used to associate a web app with an uploaded certificate.
A web app can be bound to multiple certificates.

## EXAMPLES

### Example 1: Get SSL bindings for a web app
```
PS C:\> Get-AzureRmWebAppSSLBinding -ResourceGroupName "Contoso" -WebAppName "ContosoWebApp"
```

This command retrieves the SSL bindings for the web app named "ContosoWebApp" in the "Contoso" resource group.

## PARAMETERS

### -Name
Specifies the name of the SSL binding.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group to which the certificate is assigned.
You cannot use the *ResourceGroupName* parameter and the *WebApp* parameter in the same command.

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Specifies the name of the slot to which the web app is deployed.

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
Specifies a **WebApp** object that contains details about the web app.

```yaml
Type: Site
Parameter Sets: S2
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WebAppName
Specifies the name of the web app for which this cmdlet gets SSL bindings.
You cannot use the *WebAppName* parameter and the *WebApp* parameter in the same command.

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.WebSites.Models.Site

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-AzureRmWebApp](./Get-AzureRmWebApp.md)

[New-AzureRmWebAppSSLBinding](./New-AzureRmWebAppSSLBinding.md)

[Remove-AzureRmWebAppSSLBinding](./Remove-AzureRmWebAppSSLBinding.md)
