---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version: .\New-AzureApiManagementVirtualNetwork.md
schema: 2.0.0
---

# Set-AzureApiManagementVirtualNetworks

## SYNOPSIS
Sets the VPN configuration for an API Management Service.

## SYNTAX

```
Set-AzureApiManagementVirtualNetworks -ResourceGroupName <String> -Name <String>
 [-VirtualNetworks <PsApiManagementVirtualNetwork[]>] [-PassThru] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureApiManagementVirtualNetworks** cmdlet sets Virtual Network configuration for an API Management service.

## EXAMPLES

### Example 1: Set virtual networks for an API Management service
```
PS C:\>Set-AzureApiManagementVirtualNetworks -ResourceGroupName "ContosoGroup" -Name "ContosoApi" -VirtualNetworks $VirtualNetworks
```

This command sets virtual networks for an API Management service.

## PARAMETERS

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

### -Name
Specifies the name of an API Management service.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

[New-AzureApiManagementVirtualNetwork](.\New-AzureApiManagementVirtualNetwork.md)

