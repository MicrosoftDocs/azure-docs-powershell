---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmApiManagementProduct

## SYNOPSIS
Gets a list of API Management products or a specific API Management product.

## SYNTAX

### Get all producst (Default)
```
Get-AzureRmApiManagementProduct -Context <PsApiManagementContext> [<CommonParameters>]
```

### Get by Id
```
Get-AzureRmApiManagementProduct -Context <PsApiManagementContext> -ProductId <String> [<CommonParameters>]
```

### Get by Title
```
Get-AzureRmApiManagementProduct -Context <PsApiManagementContext> [-Title <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagementProduct** cmdlet gets a list of API Management products or a specific API Management product.

## EXAMPLES

### Example 1: Get all API Management products
```
PS C:\> Get-AzureRmApiManagementProduct -Context $APImContext
```

This command gets all API Management products.

### Example 2: Get an API Management product by ID
```
PS C:\> Get-AzureRmApiManagementProduct -Context $APImContext -ProductId "0123456789"
```

This command gets the API Management product identified by the ID "0123456789".

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

### -ProductId
Specifies the ID of the product to get.

```yaml
Type: String
Parameter Sets: Get by Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Title
Specifies the title of the product to get.

```yaml
Type: String
Parameter Sets: Get by Title
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

[New-AzureRmApiManagementProduct](./New-AzureRmApiManagementProduct.md)

[Remove-AzureRmApiManagementProduct](./Remove-AzureRmApiManagementProduct.md)

[Set-AzureRmApiManagementProduct](./Set-AzureRmApiManagementProduct.md)
