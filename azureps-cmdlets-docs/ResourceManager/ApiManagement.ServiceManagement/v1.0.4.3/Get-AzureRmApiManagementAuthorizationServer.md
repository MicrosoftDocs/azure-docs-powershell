---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmApiManagementAuthorizationServer

## SYNOPSIS
Gets all Azure API Management authorization servers or a specific authorization server.

## SYNTAX

```
Get-AzureRmApiManagementAuthorizationServer -Context <PsApiManagementContext> [-ServerId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagementAuthorizationServer** cmdlet gets all Azure API Management authorization servers or a specific authorization server.

## EXAMPLES

### Example 1: Get all authorization servers
```
PS C:\> Get-AzureRmApiManagementAuthrizarionServer -Context $ApiMgmtContext
```

This command gets all API Management authorization servers.

### Example 2: Get a specific authorization server
```
PS C:\> Get-AzureRmApiManagementCertificate -Context $ApiMgmtContext -ServerId "0123456789"
```

This command gets the authorization server identified by the ID "0123456789".

## PARAMETERS

### -Context
Specifies an **PsApiManagementContext** object that contains details about the context of the Azure API Management service.

```yaml
Type: PsApiManagementContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerId
Specifies the ID of the authorization server to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

## OUTPUTS

### System.Collections.Generic.IList

## NOTES

## RELATED LINKS

[New-AzureRmApiManagementAuthorizationServer](./New-AzureRmApiManagementAuthorizationServer.md)

[Remove-AzureRmApiManagementAuthorizationServer](./Remove-AzureRmApiManagementAuthorizationServer.md)

[Set-AzureRmApiManagementAuthorizationServer](./Set-AzureRmApiManagementAuthorizationServer.md)
