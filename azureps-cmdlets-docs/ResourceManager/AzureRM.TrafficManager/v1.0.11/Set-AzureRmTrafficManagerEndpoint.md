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
The **Set-AzureRmTrafficManagerEndpoint** cmdlet updates an endpoint in Azure Traffic Manager.

## EXAMPLES

### Example 1: Update the weight of an endpoint
```
PS C:\> $MyTrafficManagerEndpoint = Get-AzureRmTrafficManagerEndpoint -Name "endpoint1" -Type AzureEndpoints -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> $MyTrafficManagerEndpoint.Weight = 20
PS C:\> Set-AzureRmTrafficManagerEndpoint -TrafficManagerEndpoint $MyTrafficManagerEndpoint
```

The **Get-AzureRmTrafficManagerEndpoint** cmdlet gets the endpoint named "endpoint1" and the returned object is stored locally in the *$MyTrafficManagerEndpoint* variable.
The weight is changed in the local endpoint object.
The updated object is passed in the *TrafficManagerEndpoint* parameter of the **Set-AzureRmTrafficManagerEndpoint** cmdlet to update the endpoint in Traffic Manager to match the local endpoint object.

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

[Get-AzureRmTrafficManagerEndpoint](./Get-AzureRmTrafficManagerEndpoint.md)

[Remove-AzureRmTrafficManagerEndpoint](./Remove-AzureRmTrafficManagerEndpoint.md)
