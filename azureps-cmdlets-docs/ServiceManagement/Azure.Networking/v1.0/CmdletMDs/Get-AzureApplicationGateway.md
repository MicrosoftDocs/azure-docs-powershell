---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\New-AzureApplicationGateway.md
schema: 2.0.0
---

# Get-AzureApplicationGateway

## SYNOPSIS
Gets an Application Gateway.

## SYNTAX

```
Get-AzureApplicationGateway [[-Name] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGateway** cmdlet gets an existing azure_2 Application Gateway.

## EXAMPLES

### Example 1: Get an Application Gateway
```
PS C:\>Get-AzureApplicationGateway -Name "ApplicationGateway06"
```

This command gets the Application Gateway named ApplicationGateway06.

### Example 2: Get all Application Gateways
```
PS C:\>Get-AzureApplicationGateway
```

This command gets all the Application Gateways under your subscription.

## PARAMETERS

### -Name
Specifies the name of the Application Gateway that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGateway, IEnumerable<Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGateway>

## NOTES

## RELATED LINKS

[New-AzureApplicationGateway](.\New-AzureApplicationGateway.md)

[Remove-AzureApplicationGateway](.\Remove-AzureApplicationGateway.md)

[Start-AzureApplicationGateway](.\Start-AzureApplicationGateway.md)

[Stop-AzureApplicationGateway](.\Stop-AzureApplicationGateway.md)

[Update-AzureApplicationGateway](.\Update-AzureApplicationGateway.md)

