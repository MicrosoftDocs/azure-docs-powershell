---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRmTrafficManagerEndpoint

## SYNOPSIS
Updates an endpoint in Azure Traffic Manager.

## SYNTAX

```
Set-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint <TrafficManagerEndpoint> [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmTrafficManagerEndpoint** updates an endpoint in Azure Traffic Manager.

## EXAMPLES

### Example 1: Update the weight of an endpoint
```
$TrafficManagerEndpoint = Get-AzureRmTrafficManagerEndpoint -Name "endpoint1" -Type AzureEndpoints -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11"
$TrafficManagerEndpoint.Weight = 20
Set-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint $TrafficManagerEndpoint
```

This example updates the weight of the endpoint named "endpoint1" in the resource group named "ResourceGroup11".

The **Get-AzureRmTrafficManagerEndpoint** cmdlet gets the endpoint named "endpoint1", which is stored locally in the $TrafficManagerEndpoint variable.
The weight is changed in the local endpoint object.
The updated object is passed in the **TrafficManagerEndpoint** parameter of the **Set-AzureRmTrafficManagerEndpoint** cmdlet to update the endpoint in Traffic Manager to match the local endpoint object.

## PARAMETERS

### -TrafficManagerEndpoint
Specifies a **TrafficManagerEndpoint** object that contains the updated details of the endpoint.
This cmdlet updates Traffic Manager to match this local object.

```yaml
Type: TrafficManagerEndpoint
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

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint
This cmdlet accepts a **TrafficManagerEndpoint** object from the pipeline.

## OUTPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint
This cmdlet returns a **TrafficManagerEndpoint** object.

## NOTES

## RELATED LINKS

[Add-AzureRmTrafficManagerEndpointConfig](./Add-AzureRmTrafficManagerEndpointConfig.md)

[Remove-AzureRmTrafficManagerEndpoint](./Remove-AzureRmTrafficManagerEndpoint.md)

[Get-AzureRmTrafficManagerEndpoint](./Get-AzureRmTrafficManagerEndpoint.md)
