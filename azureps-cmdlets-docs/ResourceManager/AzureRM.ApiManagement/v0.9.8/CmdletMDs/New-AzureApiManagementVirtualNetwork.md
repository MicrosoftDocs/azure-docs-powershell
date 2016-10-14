---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version: .\Set-AzureApiManagementVirtualNetworks.md
schema: 2.0.0
---

# New-AzureApiManagementVirtualNetwork

## SYNOPSIS
Creates an instance of PsApiManagementVirtualNetwork.

## SYNTAX

```
New-AzureApiManagementVirtualNetwork -Location <String> -SubnetName <String> -VnetId <Guid>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureApiManagementVirtualNetwork cmdlet is a helper command to create an instance of PsApiManagementVirtualNetwork.
This command is used with the Set-AzureApiManagementVirtualNetworks cmdlet.

## EXAMPLES

### Example 1: Create a virtual network
```
PS C:\>$VirtualNetworks = @()
PS C:\> $VirtualNetworks += New-AzureApiManagementVirtualNetwork -Location "East US" -SubnetName "ContosoNet" -VnetId "089D3F4D-B986-4DFD-9259-9112BA7A1F03"
PS C:\> Set-AzureApiManagementVirtualNetworks -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetworks $VirtualNetworks
```

This example creates a virtual network and then calls the **Set-AzureApiManagementVirtualNetworks** cmdlet.

## PARAMETERS

### -Location
Specifies the location of the virtual network in which this cmdlet creates the instance.

Valid values are: 

- North Central US
- South Central US
- Central US
- West Europe
- North Europe
- West US
- East US
- East US 2
- Japan East
- Japan West
- Brazil South
- Southeast Asia
- East Asia
- Australia East
- Australia Southeast

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
Specifies the identifier of the virtual network.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureApiManagementVirtualNetworks](.\Set-AzureApiManagementVirtualNetworks.md)

