---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureApplicationGatewayConfig.md
schema: 2.0.0
---

# Set-AzureApplicationGatewayConfig

## SYNOPSIS
Configures an application gateway.

## SYNTAX

### configFile
```
Set-AzureApplicationGatewayConfig -Name <String> [-ConfigFile] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### configObject
```
Set-AzureApplicationGatewayConfig -Name <String> [-Config] <ApplicationGatewayConfiguration>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureApplicationGatewayConfig** cmdlet configures an application gateway.

## EXAMPLES

### Example 1: Configure an application gateway by using a configuration object
```
PS C:\>$ConfigReturnObject = Get-AzureApplicationGatewayConfig -Name "ApplicationGateway02"
PS C:\> Set-AzureApplicationGatewayConfig -Name "ApplicationGateway06" -Config $ConfigReturnObject
```

The first command gets the configuration object for the application gateway named ApplicationGateway02 by using the Get-AzureApplicationGatewayConfig cmdlet.
The command stores it in the $ConfigReturnObject variable.

The second command sets the configuration for the application named ApplicationGateway06 by using an application gateway configuration object stored in the $ConfigReturnObject variable.

### Example 2: Configure an application gateway by using a configuration file
```
PS C:\>Set-AzureApplicationGatewayConfig -Name "ApplicationGateway06" -ConfigFile "D:\config.xml"
```

This command sets the configuration for the application named ApplicationGateway06 by using an application gateway configuration file in the specified location.

### Example 3: Modify a configuration by using a configuration object
```
PS C:\>$ConfigReturnObject = Get-AzureApplicationGatewayConfig -Name "ApplicationGateway06"
PS C:\> $ConfigReturnObject.Config.FrontendPorts[0].Port = 443
PS C:\> $ConfigReturnObject | Set-AzureApplicationGatewayConfig -Name "ApplicationGateway06"
```

The first command gets the configuration object for the application gateway named ApplicationGateway06 by using the Get-AzureApplicationGatewayConfig cmdlet.
The command stores it in the $ConfigReturnObject variable.

The second command assigns a port value to a **Port** property in the object stored in $ConfigReturnObject.

The final command passes the updated $ConfigReturnObject to the current cmdlet.

## PARAMETERS

### -Name
Specifies the name of the application gateway that this cmdlet configures.

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

### -Config
Specifies an application gateway configuration object.
This cmdlet assigns the configuration that this parameter specifies to an application gateway.

```yaml
Type: ApplicationGatewayConfiguration
Parameter Sets: configObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigFile
Specifies the path of a configuration file, in XML format, for an application gateway.
This cmdlet assigns the configuration that this parameter specifies to an application gateway.

```yaml
Type: String
Parameter Sets: configFile
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
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

### System.String, Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayConfiguration

## OUTPUTS

### Microsoft.WindowsAzure.Management.ApplicationGateway.Models.ApplicationGatewayOperationResponse

## NOTES

## RELATED LINKS

[Get-AzureApplicationGatewayConfig](.\Get-AzureApplicationGatewayConfig.md)

