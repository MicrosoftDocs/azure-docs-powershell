---
external help file: Microsoft.Azure.Commands.Cdn.dll-Help.xml
online version: .\New-AzureRmCdnEndpoint.md
schema: 2.0.0
---

# Get-AzureRmCdnEndpoint

## SYNOPSIS
Gets a CDN endpoint.

## SYNTAX

```
Get-AzureRmCdnEndpoint -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRMCdnEndpoint** cmdlet gets an azure_2 Content Delivery Network (CDN) endpoint and its associated configuration data.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -EndpointName
Specifies the name of the endpoint.
The name of the endpoint is not the host name of the endpoint.

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

### -ProfileName
Specifies the name of the profile to which the endpoint belongs.

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

### -ResourceGroupName
Specifies the name of the resource group to which the endpoint belongs.

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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

###  
This cmdlet returns an endpoint object.

## NOTES

## RELATED LINKS

[New-AzureRmCdnEndpoint](.\New-AzureRmCdnEndpoint.md)

[Remove-AzureRmCdnEndpoint](.\Remove-AzureRmCdnEndpoint.md)

[Set-AzureRmCdnEndpoint](.\Set-AzureRmCdnEndpoint.md)

[Start-AzureRmCdnEndpoint](.\Start-AzureRmCdnEndpoint.md)

[Stop-AzureRmCdnEndpoint](.\Stop-AzureRmCdnEndpoint.md)

