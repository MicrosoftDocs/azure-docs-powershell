---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Add-AzureRmApiManagementApiToProduct

## SYNOPSIS
Adds an API to a product.

## SYNTAX

```
Add-AzureRmApiManagementApiToProduct -Context <PsApiManagementContext> -ProductId <String> -ApiId <String>
 [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureRmApiManagementApiToProduct** cmdlet adds an API to a product.

## EXAMPLES

### Example 1: Add an API to the specified product
```
PS C:\> Add-AzureRmApiManagementApiToProduct -Context $ApiMgmtContext -ProductId "0123456789" -ApiId "0001"
```

This command adds the specified API to the product identified by the ID "0123456789".

## PARAMETERS

### -ApiId
Specifies the ID of an API to be added to a product.

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

### -PassThru
Specifies whether to return an object representing the API that is added.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductId
Specifies the ID of the product to which the API is being added.

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

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

## OUTPUTS

### None or an object representing the API that was added.
When you use the *PassThru* parameter, this cmdlet returns an object that represents the added API.
Otherwise, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Remove-AzureRmApiManagementApiFromProduct](./Remove-AzureRmApiManagementApiFromProduct.md)
