---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureRouteConfig.md
schema: 2.0.0
---

# Get-AzureRouteConfig

## SYNOPSIS
Gets routes from a route table.

## SYNTAX

```
Get-AzureRouteConfig [-Name <String>] -RouteTable <PSRouteTable> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRouteConfig** cmdlet gets routes from an Azure route table.
You can specify a route by name.

## EXAMPLES

### Example 1: Get a route table
```
PS C:\>Get-AzureRouteTable -ResourceGroupName "ResourceGroup11" -Name "routetable01" | Get-AzureRouteConfig -Name "route07"

Name              : route07
Id                : 
Etag              : 
ProvisioningState : 
AddressPrefix     : 10.1.0.0/16
NextHopType       : VnetLocal
NextHopIpAddress  :
```

This command gets the route table named routetable01 by using the Get-AzureRouteTable cmdlet.
The command passes that table to the current cmdlet by using the pipeline operator.
The current cmdlet gets the route named route07 in the route table named routetable01.

## PARAMETERS

### -Name
Specifies the name of the route that this cmdlet gets.

```yaml
Type: String
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

### -RouteTable
Specifies the route table from which this cmdlet gets routes.

```yaml
Type: PSRouteTable
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRouteConfig](.\Add-AzureRouteConfig.md)

[Get-AzureRouteTable](.\Get-AzureRouteTable.md)

[New-AzureRouteConfig](.\New-AzureRouteConfig.md)

[Remove-AzureRouteConfig](.\Remove-AzureRouteConfig.md)

[Set-AzureRouteConfig](.\Set-AzureRouteConfig.md)

