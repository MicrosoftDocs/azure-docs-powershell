---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: .\Get-AzureRmApiManagementApi.md
schema: 2.0.0
---

# Export-AzureRmApiManagementApi

## SYNOPSIS
Exports an API to a file.

## SYNTAX

### Export to pipeline (Default)
```
Export-AzureRmApiManagementApi -Context <PsApiManagementContext> -ApiId <String>
 -SpecificationFormat <PsApiManagementApiFormat> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Export to File
```
Export-AzureRmApiManagementApi -Context <PsApiManagementContext> -ApiId <String>
 -SpecificationFormat <PsApiManagementApiFormat> -SaveAs <String> [-Force] [-PassThru]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-AzureRmApiManagementApi** cmdlet exports an azure_2 API Management API to a file in one of the supported formats.

## EXAMPLES

### Example 1: Export an API in Web Application Description Language (WADL) format
```
PS C:\>Export-AzureRmApiManagementApi -Context $ApiMgmtContext -ApiId "0123456789" -SpecificationFormat "Wadl" -SaveAs "C:\contoso\specifications\0123456789.wadl"
```

This command exports an API to a WADL file.

## PARAMETERS

### -Context
Specifies a **PsApiManagementContext** object.

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

### -ApiId
Specifies the ID of the API to export.

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

### -SpecificationFormat
Specifies the API format.
psdx_paramvalues Wadl and Swagger.

```yaml
Type: PsApiManagementApiFormat
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SaveAs
Specifies the file path to which to save the exported API.

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

### -Force
Indicates that this operation overwrites the file of the same name if it already exists.

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
Indicates that this operation returns $True if the API is exported successfully, or $False otherwise.

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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns the exported API content as a string.

## NOTES

## RELATED LINKS

[Get-AzureRmApiManagementApi](.\Get-AzureRmApiManagementApi.md)

[Import-AzureRmApiManagementApi](.\Import-AzureRmApiManagementApi.md)

[New-AzureRmApiManagementApi](.\New-AzureRmApiManagementApi.md)

[Remove-AzureRmApiManagementApi](.\Remove-AzureRmApiManagementApi.md)

[Set-AzureRmApiManagementApi](.\Set-AzureRmApiManagementApi.md)

