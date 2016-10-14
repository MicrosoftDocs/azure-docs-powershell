---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Start-AzureApplicationGateway.md
schema: 2.0.0
---

# Set-AzureApplicationGateway

## SYNOPSIS
Updates an application gateway.

## SYNTAX

```
Set-AzureApplicationGateway -ApplicationGateway <PSApplicationGateway> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureApplicationGateway** cmdlet updates an Azure application gateway.

## EXAMPLES

### Example 1: Update an application gateway
```
PS C:\> $UpdatedAppGw = Set-AzureApplicationGateway -ApplicationGateway $AppGw
```

This command updates the application gateway with settings in the $AppGw variable and stores the updated gateway in the $UpdatedAppGw variable.

## PARAMETERS

### -ApplicationGateway
Specifies an application gateway object representing the state to which the application gateway should be set.

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

[Start-AzureApplicationGateway](.\Start-AzureApplicationGateway.md)

