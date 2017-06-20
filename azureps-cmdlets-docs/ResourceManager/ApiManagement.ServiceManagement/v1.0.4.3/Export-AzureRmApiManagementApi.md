---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Export-AzureRmApiManagementApi

## SYNOPSIS
Exports an API to a file in one of the supported formats.

## SYNTAX

### Export to pipeline (Default)
```
Export-AzureRmApiManagementApi -Context <PsApiManagementContext> -ApiId <String>
 -SpecificationFormat <PsApiManagementApiFormat> [<CommonParameters>]
```

### Export to File
```
Export-AzureRmApiManagementApi -Context <PsApiManagementContext> -ApiId <String>
 -SpecificationFormat <PsApiManagementApiFormat> -SaveAs <String> [-Force] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Export-AzureRmApiManagementApi** cmdlet exports an API to a file in one of the supported formats.

## EXAMPLES

### Example 1: Export an API in WADL format
```
PS C:\> Export-AzureRmApiManagementApi -Context $ApiMgmtContext -ApiId "0123456789" -SpecificationFormat "Wadl" -SaveAs "C:\contoso\specifications\0123456789.wadl"
```

This command exports the API identified by the ID "0123456789" to a Web Application Description Language (WADL) file.

## PARAMETERS

### -ApiId
Specifies the ID of an API to be exported.

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

### -Force
Indicates whether to forcefully overwrite the file, if it already exists.

```yaml
Type: SwitchParameter
Parameter Sets: Export to File
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies whether to return an object representing the API that is exported.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: Export to File
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SaveAs
Specifies the path and name of the file to which to export the API.

```yaml
Type: String
Parameter Sets: Export to File
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SpecificationFormat
Specifies the format of the file.

```yaml
Type: PsApiManagementApiFormat
Parameter Sets: (All)
Aliases:
Accepted values: Wadl, Swagger

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

### System.String

## NOTES

## RELATED LINKS

[Get-AzureRmApiManagementApi](./Get-AzureRmApiManagementApi.md)

[Import-AzureRmApiManagementApi](./Import-AzureRmApiManagementApi.md)

[New-AzureRmApiManagementApi](./New-AzureRmApiManagementApi.md)

[Remove-AzureRmApiManagementApi](./Remove-AzureRmApiManagementApi.md)

[Set-AzureRmApiManagementApi](./Set-AzureRmApiManagementApi.md)
