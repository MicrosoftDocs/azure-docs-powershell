---
external help file: RMAzure_Apimanagement.xml
online version: b3b67164-7adf-4fe3-87ab-51dcd46ed084
schema: 2.0.0
---

# Get-AzureRmApiManagement
## SYNOPSIS
Gets a list or a particular API Management Service description.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRmApiManagement -Name <String> -ResourceGroupName <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRmApiManagement -ResourceGroupName <String>
```

## DESCRIPTION
The **Get-AzureRmApiManagement** cmdlet gets a list of all API Management services under subscription or specified resource group or a particular API Management.

## EXAMPLES

### Example 1: Get all API Management services
```
PS C:\>Get-AzureRmApiManagement
```

This command gets all API Management services within a subscription.

### Example 2: Get all API Management services by a specific name
```
PS C:\>Get-AzureRmApiManagement -ResourceGroupName "ContosoGroup" -Name "ContosoApi"
```

This command gets all API Management service by name.

## PARAMETERS

### -Name
Specifies the name of API Management service.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group under in which this cmdlet gets the API Management service.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Backup-AzureRmApiManagement](b3b67164-7adf-4fe3-87ab-51dcd46ed084)

[New-AzureRmApiManagement](6b5595ca-246e-4381-a37e-24dfae307109)

[Remove-AzureRmApiManagement](9a2c4617-9870-4d9c-92fa-2af03211d931)

[Restore-AzureRmApiManagement](b0ff412d-269a-472f-8d79-9c0b9f0ebac2)

