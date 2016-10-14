---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Stop-AzureApplicationGateway.md
schema: 2.0.0
---

# Get-AzureApplicationGateway

## SYNOPSIS
Gets an application gateway.

## SYNTAX

```
Get-AzureApplicationGateway [-Name <String>] [-ResourceGroupName <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGateway** cmdlet gets an application gateway.

## EXAMPLES

### Example 1: Get a specified application gateway
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
```

This command gets the application gateway named ApplicationGateway01 that belongs to the resource group named ResourceGroup01 and stores it in the $AppGw variable.

### Example 2: Get a list of application gateways in a resource group
```
PS C:\> $AppGwList = Get-AzureApplicationGateway -ResourceGroupName "ResourceGroup01"
```

This command gets a list of all the application gateways in the resource group named ResourceGroup01 and stores it in the $AppGwList variable.

### Example 3: Get a list of application gateways in a subscription
```
PS C:\> $AppGwList = Get-AzureApplicationGateway
```

This command gets a list of all the application gateways in the subscription and stores it in the $AppGwList variable.

## PARAMETERS

### -Name
Specifies the name of the application gateway that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ResourceGroupName
Specifies the name of the resource group that contains the application gateway.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGateway>

## NOTES

## RELATED LINKS

[Stop-AzureApplicationGateway](.\Stop-AzureApplicationGateway.md)

