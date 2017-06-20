---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRmApiManagementVirtualNetwork

## SYNOPSIS
Creates an instance of **PsApiManagementVirtualNetwork**.

## SYNTAX

```
New-AzureRmApiManagementVirtualNetwork -Location <String> -SubnetName <String> -VnetId <Guid>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmApiManagementVirtualNetwork** cmdlet creates an instance of **PsApiManagementVirtualNetwork**.
This cmdlet is a helper command that is used with the **Set-AzureRmApiManagementVirtualNetworks** cmdlet.

## EXAMPLES

### Example 1: Create a virtual network
```
PS C:\> $VirtualNetworks = @()
PS C:\> $VirtualNetworks += New-AzureRmApiManagementVirtualNetwork -Location "East US" -SubtenName "ContosoNet" -VnetId "089D3F4D-B986-4DFD-9259-9112BA7A1F03"
PS C:\> Set-AzureRmApiManagementVirtualNetworks -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetworks $VirtualNetworks
```

This example creates a virtual network with a sub network named "ContosoNet"
and then calls the **Set-AzureRmApiManagementVirtualNetworks** cmdlet to set the virtual network configuration for an API Management service.

## PARAMETERS

### -Location
Specifies the location of the virtual network in which this cmdlet creates the instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: North Central US, South Central US, Central US, West Europe, North Europe, West US, East US, East US 2, Japan East, Japan West, Brazil South, Southeast Asia, East Asia, Australia East, Australia Southeast

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Specifies the name of the sub network.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VnetId
Specifies an ID for the virtual network.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementVirtualNetwork

## NOTES

## RELATED LINKS

[Set-AzureRmApiManagementVirtualNetworks](./Set-AzureRmApiManagementVirtualNetworks.md)
