---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-AzureRmApiManagementPolicy

## SYNOPSIS
Removes the API Management policy for the specified scope.

## SYNTAX

### Tenant level (Default)
```
Remove-AzureRmApiManagementPolicy -Context <PsApiManagementContext> [-PassThru] [-Force] [<CommonParameters>]
```

### Product level
```
Remove-AzureRmApiManagementPolicy -Context <PsApiManagementContext> -ProductId <String> [-PassThru] [-Force]
 [<CommonParameters>]
```

### API level
```
Remove-AzureRmApiManagementPolicy -Context <PsApiManagementContext> -ApiId <String> [-PassThru] [-Force]
 [<CommonParameters>]
```

### Operation level
```
Remove-AzureRmApiManagementPolicy -Context <PsApiManagementContext> -ApiId <String> -OperationId <String>
 [-PassThru] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmApiManagementPolicy** cmdlet removes the API Management policy for the specified scope.

## EXAMPLES

### Example 1: Remove the tenant-level policy
```
PS C:\> Remove-AzureRmApiManagementPolicy -Context $APImContext
```

This command removes tenant-level policy from API Management.

### Example 2: Remove the product-scope policy
```
PS C:\> Remove-AzureRmApiManagementPolicy -Context $APImContext -ProductId "0123456789"
```

This command removes product-scope policy for the product identified by the ID "0123456789".

### Example 3: Remove the API-scope policy
```
PS C:\> Remove-AzureRmApiManagementPolicy -Context $APImContext -ApiId "9876543210"
```

This command removes API-scope policy for the API identified by the ID "9876543210".

### Example 4: Remove the operation-scope policy
```
PS C:\> Remove-AzureRmApiManagementPolicy -Context $APImContext -ApiId "9876543210" -OperationId "777"
```

This command removes operation-scope policy for the operation identified by the ID "777".

## PARAMETERS

### -ApiId
Specifies the ID of an API.
If this parameter is included, the cmdlet removes the API-scope policy.

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
Indicates whether to run this command without asking for user confirmation.

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

### -OperationId
Specifies the ID of an API operation.
If this parameter is included with the *ApiId* parameter, the cmdlet removes operation-scope policy.

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

### -PassThru
Specifies whether to return an object representing the item removed.

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
Specifies the ID of a product.
If this parameter is included, the cmdlet removes the product-scope policy.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
### System.String

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzureRmApiManagementPolicy](./Get-AzureRmApiManagementPolicy.md)

[Set-AzureRmApiManagementPolicy](./Set-AzureRmApiManagementPolicy.md)
