---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: e6aee046-e491-41d0-9b71-9bd70f98e9d7
schema: 2.0.0
---

# Stop-AzureApplicationGateway

## SYNOPSIS
Stops an application gateway

## SYNTAX

```
Stop-AzureApplicationGateway -ApplicationGateway <PSApplicationGateway> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### Example 1: Stop an application gateway
```
PS C:\> $AppGw = Stop-AzureApplicationGateway -ApplicationGateway $AppGw
```

This command stops the application gateway stored in the $AppGw variable.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway to stop.```yaml
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

### System.String

## OUTPUTS

## NOTES

## RELATED LINKS

