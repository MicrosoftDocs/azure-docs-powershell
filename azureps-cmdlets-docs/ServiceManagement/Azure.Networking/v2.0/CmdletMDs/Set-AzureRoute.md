---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Remove-AzureRoute.md
schema: 2.0.0
---

# Set-AzureRoute

## SYNOPSIS
Creates a route in a route table.

## SYNTAX

```
Set-AzureRoute [-RouteName] <String> [-AddressPrefix] <String> [-NextHopType] <String>
 [[-NextHopIpAddress] <String>] [-RouteTable] <IRouteTable> [-Profile <AzureSMProfile>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRoute** cmdlet creates a route in a route table.
The new route takes effect almost immediately on the virtual machines that are associated with the route table.

## EXAMPLES

### Example 1: Add a virtual appliance next hop route
```
PS C:\>New-AzureRouteTable -Name "ApplianceRouteTable" -Location "Central US" -Label "Appliance Route Table" | Set-AzureRoute -RouteName "ApplianceRoute03" -AddressPrefix "10.0.0.0/24" -NextHopType VirtualAppliance -NextHopIpAddress "10.0.1.5"
Routes                        Name                          Location                      Label
------                        ----                          --------                      -----
{approute}                    AppRT                         Central US                    Appliance Route Table
```

This command creates a route table named ApplianceRouteTable in the specified location.
The command passes that route table to the current cmdlet.
The current cmdlet adds a route named ApplianceRoute03, which is a VirtualAppliance next hop type.
The command specifies the next hop IP address and the address prefix for the route.

### Example 2: Add an Internet next hop route
```
PS C:\>Get-AzureRouteTable -Name "ApplianceRouteTable" | Set-AzureRoute -RouteName "InternetRoute" -AddressPrefix "0.0.0.0/0" -NextHopType Internet
Routes                        Name                          Location                      Label
------                        ----                          --------                      -----
{approute, internetroute}     AppRT                         Central US                    Appliance Route Table
```

This command gets a route table named ApplianceRouteTable.
The command passes that route table to the current cmdlet.
The current cmdlet adds a route named InternetRoute, which is an Internet next hop type.
The command specifies the address prefix for the route.

## PARAMETERS

### -AddressPrefix
Specifies an address prefix for the new route.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHopIpAddress
Specifies the IP address of the appliance that is the next hop for traffic that uses this route.
Specify this value only if you specify a value of VirtualAppliance for the *NextHopType* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHopType
Specifies the next hop type for traffic that uses this route.
Valid values are: 

- VPNGateway
- VNETLocal
- Internet
- VirtualAppliance
- Null

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Not Specified```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

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
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteName
Specifies a name for the new route that this cmdlet adds.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteTable
Specifies the route table to which this cmdlet adds the new route.

```yaml
Type: IRouteTable
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AzureRoute](.\Remove-AzureRoute.md)

