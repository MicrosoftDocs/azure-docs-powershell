---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A8AC20CE-6B28-484B-8CE4-A950B54C92EA
---

# Get-AzureRmApiManagementTenantAccess

## SYNOPSIS
Gets the access configuration for a tenant.

## SYNTAX

```
Get-AzureRmApiManagementTenantAccess -Context <PsApiManagementContext> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagementTenantAccess** cmdlet gets the tenant access configuration for a tenant.

## EXAMPLES

### Example 1: Get tenant access configuration
```
PS C:\>Get-AzureRmApiManagementTenantAccess -Context $ApimContext
```

This command gets the tenant access configuration for the specified context.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementAccessInformation

## NOTES

## RELATED LINKS

[Set-AzureRmApiManagementTenantAccess](./Set-AzureRmApiManagementTenantAccess.md)


