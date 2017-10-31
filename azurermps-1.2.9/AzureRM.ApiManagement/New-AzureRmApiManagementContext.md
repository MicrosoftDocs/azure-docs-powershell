---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmApiManagementContext

## SYNOPSIS
Create PsAzureApiManagementContext.

## SYNTAX

```
New-AzureRmApiManagementContext -ResourceGroupName <String> -ServiceName <String> [<CommonParameters>]
```

## DESCRIPTION
Create an instance of PsAzureApiManagementContext.
The context is to be used for all the API Management Service Management cmdlets.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}





```
$apimContext = New-AzureRmApiManagementContext -ResourceGroupName contosoresources -ServiceName contoso
```

Create an instance of PsApiManagementContext

## PARAMETERS

### -ResourceGroupName
Name of resource group under which an API Management service is deployed.

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

### -ServiceName
Name of deployed API Management service.

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

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsAzureApiManagementContext

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, api, apimanagement, apimgmt, apism

## RELATED LINKS

