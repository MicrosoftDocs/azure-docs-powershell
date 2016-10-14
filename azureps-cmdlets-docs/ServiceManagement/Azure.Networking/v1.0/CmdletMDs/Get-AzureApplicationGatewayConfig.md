---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Set-AzureApplicationGatewayConfig.md
schema: 2.0.0
---

# Get-AzureApplicationGatewayConfig

## SYNOPSIS
Gets an Application Gateway configuration context.

## SYNTAX

```
Get-AzureApplicationGatewayConfig [-Name] <String> [-ExportToFile <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGatewayConfig** cmdlet gets an azure_2 Application Gateway configuration context.
A context includes both a configuration object and XML configuration.
You can save the XML configuration to a file.

## EXAMPLES

### Example 1: Get an Application Gateway configuration and save it to a file
```
PS C:\>Get-AzureApplicationGatewayConfig -Name "ApplicationGateway06" -ExportToFile "D:\config.xml"
```

This command gets the configuration for an Application Gateway named ApplicationGateway06.
The command saves it in the file in the specified path.

## PARAMETERS

### -Name
Specifies the name of the Application Gateway for which this cmdlet gets configuration information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExportToFile
Specifies a file path to which this cmdlet saves the configuration in XML format.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

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

### System.String

## OUTPUTS

### Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayConfigContext

## NOTES

## RELATED LINKS

[Set-AzureApplicationGatewayConfig](.\Set-AzureApplicationGatewayConfig.md)

