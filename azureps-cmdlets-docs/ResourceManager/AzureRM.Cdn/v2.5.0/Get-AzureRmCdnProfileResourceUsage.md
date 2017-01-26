---
external help file: Microsoft.Azure.Commands.Cdn.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmCdnProfileResourceUsage

## SYNOPSIS
Gets resource usages under a specific CDN profile.

## SYNTAX

### Parameter Set for fields parameters (Default)
```
Get-AzureRmCdnProfileResourceUsage -ProfileName <String> -ResourceGroupName <String>
```

### Parameter Set for object parameters
```
Get-AzureRmCdnProfileResourceUsage -CdnProfile <PSProfile>
```

## DESCRIPTION
Gets resource usages under a specific CDN profile such as count and limit of endpoints.

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CdnProfile
@{Text=}

```yaml
Type: PSProfile
Parameter Sets: Parameter Set for object parameters
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProfileName
@{Text=}

```yaml
Type: String
Parameter Sets: Parameter Set for fields parameters
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
@{Text=}

```yaml
Type: String
Parameter Sets: Parameter Set for fields parameters
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.Models.PSResourceUsage

## NOTES

## RELATED LINKS

