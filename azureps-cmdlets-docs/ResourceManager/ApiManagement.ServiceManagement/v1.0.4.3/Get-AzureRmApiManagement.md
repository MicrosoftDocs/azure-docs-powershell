---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmApiManagement

## SYNOPSIS
Gets one or more Azure API Management services.

## SYNTAX

### All In Subscription (Default)
```
Get-AzureRmApiManagement [<CommonParameters>]
```

### All In Resource Group
```
Get-AzureRmApiManagement -ResourceGroupName <String> [<CommonParameters>]
```

### Specific API Management Service
```
Get-AzureRmApiManagement -ResourceGroupName <String> -Name <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagement** cmdlet gets a specific Azure API Management service or a list of all Azure API Management services that are within a subscription or that are under the specified resource group.

## EXAMPLES

### Example 1: Get all API Management services
```
PS C:\> Get-AzureRmApiManagement
```

This command gets all API Management services within a subscription.

### Example 2: Get a specific API Management service
```
PS C:\> Get-AzureRmApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
```

This command gets the API Management service named "ContosoApi" in the resource group "ContosoGroup".

## PARAMETERS

### -Name
Specifies the name of the API Management service to get.

```yaml
Type: String
Parameter Sets: Specific API Management Service
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group under which this cmdlet gets the API Management service.

```yaml
Type: String
Parameter Sets: All In Resource Group, Specific API Management Service
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

### System.Collections.Generic.List

## NOTES

## RELATED LINKS

[Backup-AzureRmApiManagement](./Backup-AzureRmApiManagement.md)

[New-AzureRmApiManagement](./New-AzureRmApiManagement.md)

[Remove-AzureRmApiManagement](./Remove-AzureRmApiManagement.md)

[Restore-AzureRmApiManagement](./Restore-AzureRmApiManagement.md)
