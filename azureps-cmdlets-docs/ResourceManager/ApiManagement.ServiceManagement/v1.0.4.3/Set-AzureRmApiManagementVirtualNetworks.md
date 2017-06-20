---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRmApiManagementVirtualNetworks

## SYNOPSIS
Sets virtual network configuration for an API Management service.

## SYNTAX

```
Set-AzureRmApiManagementVirtualNetworks -ResourceGroupName <String> -Name <String>
 [-VirtualNetworks <PsApiManagementVirtualNetwork[]>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmApiManagementVirtualNetworks** cmdlet sets virtual network configuration for an API Management service.

## EXAMPLES

### Example 1: Set virtual networks for an API Management service
```
PS C:\> Set-AzureRmApiManagementVirtualNetworks -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetworks $VirtualNetworks
```

This command sets virtual networks for the API Management service named "ContosoApi" in the resource group "ContosoGroup".

## PARAMETERS

### -Name
Specifies the name of the API Management service for which to set the virtual network configuration.

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

### -PassThru
Specifies whether to return an updated **PsApiManagement** object to the pipeline.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworks
Specifies an array of virtual network configurations.
Passing $null in this parameter will remove the virtual network configurations.
The default value is $null.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[New-AzureRmApiManagementVirtualNetwork](./New-AzureRmApiManagementVirtualNetwork.md)
