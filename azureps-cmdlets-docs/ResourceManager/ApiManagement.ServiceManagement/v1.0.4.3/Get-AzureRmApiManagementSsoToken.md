---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmApiManagementSsoToken

## SYNOPSIS
Gets a link (URL) containing a single sign-on (SSO) token for an API Management service.

## SYNTAX

```
Get-AzureRmApiManagementSsoToken -ResourceGroupName <String> -Name <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagementSsoToken** cmdlet gets a link (URL) containing a single sign-on (SSO) token to a deployed management portal of an API Management service.

## EXAMPLES

### Example 1: Get the SSO token for an API Management service
```
PS C:\> Get-AzureRmApiManagementSsoToken -ResourceGroupName "Contoso" -Name "ContosoApi"
```

This command gets the SSO token for an API Management service named "ContosoApi".

## PARAMETERS

### -Name
Specifies the name of the API Management instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group under which API Management exists.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Get-AzureRmApiManagement](./Get-AzureRmApiManagement.md)
