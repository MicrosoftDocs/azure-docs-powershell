---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Import-AzureRmApiManagementApi

## SYNOPSIS
Imports an API from a file or a URL.

## SYNTAX

### From Local File (Default)
```
Import-AzureRmApiManagementApi -Context <PsApiManagementContext> [-ApiId <String>]
 -SpecificationFormat <PsApiManagementApiFormat> -SpecificationPath <String> [-Path <String>]
 [<CommonParameters>]
```

### From URL
```
Import-AzureRmApiManagementApi -Context <PsApiManagementContext> [-ApiId <String>]
 -SpecificationFormat <PsApiManagementApiFormat> -SpecificationUrl <String> [-Path <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-AzureRmApiManagementApi** cmdlet imports an API from a file or a URL.

## EXAMPLES

### Example 1 Import an API from a WADL file
```
PS C:\> Import-AzureRmApiManagementApi -Context $ApiMgmtContext -SpecificationFormat "Wadl" -SpecificationPath "C:\contoso\specifications\echoapi.wadl" -Path "apis"
```

This command imports an API from the specified file in the Web Application Description Language (WADL) format.

### Example 2 Import an API from a Swagger file
```
PS C:\>Import-AzureRmApiManagementApi -Context $ApiMgmtContext -SpecificationFormat "Swagger" -SpecificationPath "C:\contoso\specifications\echoapi.swagger" -Path "apis"
```

This command imports an API from the specified file in the Swagger format.

### Example 3: Import an API from a WADL link
```
PS C:\>Import-AzureRmApiManagementApi -Context $ApiMgmtContext -SpecificationFormat "Wadl" -SpecificationUrl "http://contoso.com/specifications/wadl/echoapi" -Path "apis"
```

This command imports an API from the specified WADL link.

## PARAMETERS

### -ApiId
Specifies an ID for the API that is being imported.
If an ID is not specified, it will be generated.

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

### -Path
Specifies a web API path as the last part of the API's public URL.
This URL is used by API consumers for sending requests to the web service.
The value of this parameter must be 1 to 400 characters long.
The default value is $Null.

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

### -SpecificationFormat
Specifies the format of the file from which the API is being imported. Valid formats are WADL and Swagger.

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

### -SpecificationPath
Specifies the path and name of the file from which the API is being imported.

```yaml
Type: String
Parameter Sets: From Local File
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SpecificationUrl
Specifies the URL from which the API is being imported.

```yaml
Type: String
Parameter Sets: From URL
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
### System.String
### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementApiFormat

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementApi

## NOTES

## RELATED LINKS

[Export-AzureRmApiManagementApi](./Export-AzureRmApiManagementApi.md)

[Get-AzureRmApiManagementApi](./Get-AzureRmApiManagementApi.md)

[New-AzureRmApiManagementApi](./New-AzureRmApiManagementApi.md)

[Remove-AzureRmApiManagementApi](./Remove-AzureRmApiManagementApi.md)

[Set-AzureRmApiManagementApi](./Set-AzureRmApiManagementApi.md)
