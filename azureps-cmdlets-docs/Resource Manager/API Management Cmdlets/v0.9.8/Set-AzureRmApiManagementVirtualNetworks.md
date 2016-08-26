---
external help file: RMAzure_Apimanagement.xml
online version: ec96b443-15bf-4b19-b518-decb18c64749
schema: 2.0.0
---

# Set-AzureRmApiManagementVirtualNetworks
## SYNOPSIS
Sets the VPN configuration for an API Management Service.

## SYNTAX

```
Set-AzureRmApiManagementVirtualNetworks [-PassThru] [-VirtualNetworks <PsApiManagementVirtualNetwork[]>]
 -Name <String> -ResourceGroupName <String>
```

## DESCRIPTION
The **Set-AzureRmApiManagementVirtualNetworks** cmdlet sets Virtual Network configuration for an API Management service.

## EXAMPLES

### Example 1: Set virtual networks for an API Management service
```
PS C:\>Set-AzureRmApiManagementVirtualNetworks -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetworks $VirtualNetworks
```

This command sets virtual networks for an API Management service.

## PARAMETERS

### -Name
Specifies the name of an API Management service.

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
Specifies the name of the resource group under which the API Management service exists.

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

### -VirtualNetworks
Specifies an array of virtual networks configurations.
Passing $null will remove the virtual network configuration.

```yaml
Type: PsApiManagementVirtualNetwork[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureRmApiManagementVirtualNetwork](ec96b443-15bf-4b19-b518-decb18c64749)

