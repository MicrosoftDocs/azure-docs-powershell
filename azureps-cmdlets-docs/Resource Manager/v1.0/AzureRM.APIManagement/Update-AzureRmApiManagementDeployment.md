---
external help file: RMAzure_Apimanagement.xml
online version: e067ded3-a2e3-4d53-8628-0ebbafa62721
schema: 2.0.0
---

# Update-AzureRmApiManagementDeployment
## SYNOPSIS
Updates deployment of an API Management Service.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Update-AzureRmApiManagementDeployment
 [-AdditionalRegions <0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]>] [-PassThru]
 [-VirtualNetwork <PsApiManagementVirtualNetwork>] -Capacity <Int32> -Location <String> -Name <String>
 -ResourceGroupName <String> [-Sku]
```

### UNNAMED_PARAMETER_SET_2
```
Update-AzureRmApiManagementDeployment [-PassThru] -ApiManagement <PsApiManagement>
```

## DESCRIPTION
The **Update-AzureRmApiManagementDeployment** cmdlet updates current deployments of an API Management service.

## EXAMPLES

### Example 1: Update a deployment of an ApiManagement instance
```
PS C:\>Update-AzureRmApiManagementDeployment -ResourceGroupName "Contoso" -Name "ContosoApi" -Sku "Standard" -Capacity 3
```

This command updates deployment of an API Management instance to a three unit capacity standard.

### Example 2: Get an ApiManagement instance and rescale it
```
PS C:\>$ApiManagement = Get-AzureRmApiManagement -ResourceGroupName "Contoso" -Name "ContosoApi"
PS C:\> $ApiManagement.Sku = "Premium"
PS C:\> $ApiManagement.Capacity = 5
PS C:\> $ApiManagement.AddRegion("Central US", "Premium", 3)
PS C:\> Update-AzureRmApiManagementDeployment -ApiManagement $ApiManagement
```

This example gets an Api Management instance, scales it to five premium units and then adds an additional three units to the premium region.

## PARAMETERS

### -AdditionalRegions
Specifies additional deployment regions of azure_2 API Management.

```yaml
Type: 0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ApiManagement
Specifies the **PsApiManagement** instance to get deployment configuration from.
Use this parameter if the instance already has all the required changes.

```yaml
Type: PsApiManagement
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Capacity
Specifies the SKU capacity of the master azure_2 API Management deployment region.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location of the master API Management deployment region.

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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of API Management that this cmdlet updates.

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

### -PassThru
passthru

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of resource group under which API Management exists.

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

### -Sku
Specifies the tier of the master azure_2 API Management deployment region.

Valid values are: 

-- Developer
-- Standard
-- Premium

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 
Accepted values: Developer, Standard, Premium

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies the Virtual Network configuration of the master azure_2 API Management deployment region.

```yaml
Type: PsApiManagementVirtualNetwork
Parameter Sets: UNNAMED_PARAMETER_SET_1
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

[Get-AzureRmApiManagement](e067ded3-a2e3-4d53-8628-0ebbafa62721)

