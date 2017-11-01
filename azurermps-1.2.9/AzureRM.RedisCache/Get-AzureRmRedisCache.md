---
external help file: Microsoft.Azure.Commands.RedisCache.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmRedisCache

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### All In Subscription (Default)
```
Get-AzureRmRedisCache [<CommonParameters>]
```

### All In Resource Group
```
Get-AzureRmRedisCache -ResourceGroupName <String> [<CommonParameters>]
```

### Specific Redis Cache
```
Get-AzureRmRedisCache -ResourceGroupName <String> -Name <String> [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Name
Name of redis cache.

```yaml
Type: String
Parameter Sets: Specific Redis Cache
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Name of resource group under which want to create cache.

```yaml
Type: String
Parameter Sets: All In Resource Group, Specific Redis Cache
Aliases: 

Required: True
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

### System.Collections.Generic.List`1[[Microsoft.Azure.Commands.RedisCache.Models.RedisCacheAttributes, Microsoft.Azure.Commands.RedisCache, Version=1.1.2.3, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

## NOTES

## RELATED LINKS

