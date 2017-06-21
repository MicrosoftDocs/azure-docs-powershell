---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmApiManagementPolicy

## SYNOPSIS
Gets the specified API Management policy.

## SYNTAX

### Tenant level (Default)
```
Get-AzureRmApiManagementPolicy -Context <PsApiManagementContext> [-Format <String>] [-SaveAs <String>] [-Force]
 [<CommonParameters>]
```

### Product level
```
Get-AzureRmApiManagementPolicy -Context <PsApiManagementContext> [-Format <String>] [-SaveAs <String>]
 -ProductId <String> [-Force] [<CommonParameters>]
```

### API level
```
Get-AzureRmApiManagementPolicy -Context <PsApiManagementContext> [-Format <String>] [-SaveAs <String>]
 -ApiId <String> [-Force] [<CommonParameters>]
```

### Operation level
```
Get-AzureRmApiManagementPolicy -Context <PsApiManagementContext> [-Format <String>] [-SaveAs <String>]
 -ApiId <String> -OperationId <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagementPolicy** cmdlet gets the specified API Management policy.

## EXAMPLES

### Example 1: Get the tenant-level policy
```
PS C:\> Get-AzureRmApiManagementPolicy -Context $APImContext -SaveAs "C:\contoso\policies\tenantpolicy.xml"
```

This command gets tenant-level policy and saves it to a file named "tenantpolicy.xml".

### Example 2: Get the product-scope policy
```
PS C:\> Get-AzureRmApiManagementPolicy -Context $APImContext -ProductId "0123456789"
```

This command gets product-scope policy for the product identified by the ID "0123456789".

### Example 3: Get the API-scope policy
```
PS C:\> Get-AzureRmApiManagementPolicy -Context $APImContext -ApiId "9876543210"
```

This command gets API-scope policy for the API identified by the ID "9876543210".

### Example 4: Get the operation-scope policy
```
PS C:\> Get-AzureRmApiManagementPolicy -Context $APImContext -ApiId "9876543210" -OperationId "777"
```

This command gets operation-scope policy for the operation identified by the ID "777".

## PARAMETERS

### -ApiId
Specifies the ID of an API.
If this parameter is included, the cmdlet returns the API-scope policy.

```yaml
Type: String
Parameter Sets: API level, Operation level
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
Indicates whether to forcefully overwrite the file specified in the *SaveAs* parameter, if the file already exists.

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

### -Format
Specifies the format in which to save the API management policy.
The default value for this parameter is "application/vnd.ms-azure-apim.policy+xml".

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

### -OperationId
Specifies the ID of an API operation.
If this parameter is included with the *ApiId* parameter, the cmdlet returns operation-scope policy.

```yaml
Type: String
Parameter Sets: Operation level
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductId
Specifies the ID of a product.
If this parameter is included, the cmdlet returns the product-scope policy.

```yaml
Type: String
Parameter Sets: Product level
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SaveAs
Specifies the path and name of the file to which to save the policy.
If this parameter is not included, the policy will be sent to the pipeline as a sting.

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

### System.String

## NOTES

## RELATED LINKS

[Remove-AzureRmApiManagementPolicy](./Remove-AzureRmApiManagementPolicy.md)

[Set-AzureRmApiManagementPolicy](./Set-AzureRmApiManagementPolicy.md)
