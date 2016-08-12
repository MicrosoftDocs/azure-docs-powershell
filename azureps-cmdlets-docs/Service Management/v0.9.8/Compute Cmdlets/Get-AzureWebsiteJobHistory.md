---
external help file: SMAzure_Compute.xml
online version: 0c2a5092-db45-4ce7-b39b-d1e499b4a867
schema: 2.0.0
---

# Get-AzureWebsiteJobHistory
## SYNOPSIS
Gets a web job history

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureWebsiteJobHistory [[-Name] <String>] [-Slot <String>] -JobName <String> [-Latest]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureWebsiteJobHistory [[-Name] <String>] [-Slot <String>] -JobName <String>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureWebsiteJobHistory [[-Name] <String>] [-Slot <String>] -JobName <String> -RunId <String>
```

## DESCRIPTION
Gets a web job history

## EXAMPLES

### --------------  Get complete history for a web job --------------
```
C:\PS>Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob
```

Gets complete history for MyWebJob

### --------------  Get latest run for a web job --------------
```
C:\PS>Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob -Latest
```

Gets latest run info for MyWebJob

### --------------  Get specific run for a web job --------------
```
C:\PS>Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob -RunId 10
```

Gets all info about run with id 10 for MyWebJob

## PARAMETERS

### -JobName
The web job name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Latest
If specified, return the latest run history.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the Azure website

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RunId
The id of the run history you want to see

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
The slot name of the Azure website

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Get-AzureWebsiteJob](5ef76b84-385f-419e-8aba-228d53ce2232)

[New-AzureWebsiteJob](89c77daa-24fd-4b27-b624-3486fe642722)

[Remove-AzureWebsiteJob](e25091a2-2472-4674-978c-ec1522631bc1)

