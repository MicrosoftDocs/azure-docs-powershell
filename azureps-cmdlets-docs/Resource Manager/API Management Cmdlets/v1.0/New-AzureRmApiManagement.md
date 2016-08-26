---
external help file: RMAzure_Apimanagement.xml
online version: b3b67164-7adf-4fe3-87ab-51dcd46ed084
schema: 2.0.0
---

# New-AzureRmApiManagement
## SYNOPSIS
Creates an API Management deployment.

## SYNTAX

```
New-AzureRmApiManagement [-Capacity <Int32]>] [-Sku <PsApiManagementSku]>]
 [-Tags <0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]>] -AdminEmail <String> -Location <String>
 -Name <String> -Organization <String> -ResourceGroupName <String>
```

## DESCRIPTION
The **New-AzureRmApiManagement** cmdlet creates an API Management deployment in azure_2 API Management.

## EXAMPLES

### Example 1: Create at Developer tier API Management service
```
PS C:\>New-AzureRmApiManagement -ResourceGroupName "ContosoGroup02" -Name "ContosoApi" -Location "Central US" -Organization "Contoso" -AdminEmail "admin@contoso.com"
```

This command creates a Developer tier API Management service.
The command specifies the organization and the administrator address.
The command does not specify the *SKU* parameter.
Therefore, the cmdlet uses the default value of Developer.

### Example 2: Create a Standard tier service that has three units
```
PS C:\>New-AzureRmApiManagement -ResourceGroupName "ContosoGroup02 -Name "ContosoApi" -Location "Central US" -Organization "Contoso" -AdminEmail "admin@contoso.com" -Sku Standard -Capacity 3
```

This command creates a Standard tier API Management service that has three units.

## PARAMETERS

### -AdminEmail
Specifies the originating email address for all notifications that the API Management system sends.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Capacity
Specifies the SKU capacity of the azure_2 API Management service.
The default is one (1).

```yaml
Type: Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location in which this cmdlet creates an API Management deployment.
To obtain valid locations, use the Get-AzureLocation cmdlets.

Valid values are: 

-- North Central US
-- South Central US
-- Central US
-- West Europe
-- North Europe
-- West US
-- East US
-- East US 2
-- Japan East
-- Japan West
-- Brazil South
-- Southeast Asia
-- East Asia
-- Australia East
-- Australia Southeast

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the API Management deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Organization
Specifies the name of an organization.
API Management uses this address in the developer portal in email notifications.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the of resource group under which this cmdlet creates an API Management deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Specifies the tier of the API Management service.
Valid values are: 

-- Developer 
-- Standard 
-- Premium 

The default is Developer.

```yaml
Type: PsApiManagementSku]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Tags
Specifies a dictionary of tags.

```yaml
Type: 0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Backup-AzureRmApiManagement](b3b67164-7adf-4fe3-87ab-51dcd46ed084)

[Get-AzureRmApiManagement](e067ded3-a2e3-4d53-8628-0ebbafa62721)

[Remove-AzureRmApiManagement](9a2c4617-9870-4d9c-92fa-2af03211d931)

[Restore-AzureRmApiManagement](b0ff412d-269a-472f-8d79-9c0b9f0ebac2)

