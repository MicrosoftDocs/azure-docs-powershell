---
external help file: RMAzure_Apimanagement.xml
online version: a6e4fc8a-f5c6-4f8e-8ed9-5ee80150b119
schema: 2.0.0
---

# Remove-AzureRmApiManagementRegion
## SYNOPSIS
Removes an existing deployment region from PsApiManagement instance.

## SYNTAX

```
Remove-AzureRmApiManagementRegion -ApiManagement <PsApiManagement> -Location <String>
```

## DESCRIPTION
The **Remove-AzureRmApiManagementRegion** cmdlet removes instance of type **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion** from a collection of **AdditionalRegions** of provided the instance of type **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
This cmdlet does not modify deployment by itself but updates the instance of **PsApiManagement** in-memory.
To update a deployment of an API Management, pass the modified **PsApiManagementInstance** to **Update-AzureRmApiManagement**.

## EXAMPLES

### Example 1: Remove a region from a PsApiManagement instance
```
PS C:\>Remove-AzureRmApiManagementRegion -ApiManagement $ApiManagement -Location "East US"
```

This command removes the region named East US from the **PsApiManagement** instance.

### Example 2: Remove a region from a PsApiManagement instance using a series of commands
```
PS C:\>Get-AzureRmApiManagement -ResourceGroupName "Contoso" -Name ContosoApi | Remove-AzureRmApiManagementRegion -Location "East US" | Update-AzureRmApiManagementDeployment
```

This first command gets an instance of **PsApiManagement** from the resource group named Contoso named ContosoApi.
The final command then removes the region named East US from that instance then updates the deployment.

## PARAMETERS

### -ApiManagement
Specifies the **PsApiManagement** instance that this cmdlet removes the additional deployment region from.

```yaml
Type: PsApiManagement
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Location
Specifies the location of the region that this cmdlet removes.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRmApiManagementRegion](a6e4fc8a-f5c6-4f8e-8ed9-5ee80150b119)

[Update-AzureRmApiManagementRegion](bf37a79f-38a4-433e-b847-beb564ad781c)

