---
external help file: SMAzure_Compute.xml
online version: 3997c3b8-37ce-4135-a17d-63ae3bdd8e74
schema: 2.0.0
---

# Remove-AzureWebsiteJob
## SYNOPSIS
Removes an existing web job for a website

## SYNTAX

```
Remove-AzureWebsiteJob [[-Name] <String>] [-Force] [-Slot <String>] -JobName <String> [-JobType]
```

## DESCRIPTION
Removes an existing web job for a website

## EXAMPLES

### --------------  Remove an existing web job for a website --------------
```
C:\PS>Remove-AzureWebsiteJob -Name MyWebsite -JobName MyWebJob -JobType Continuous
```

Removes a web job called MyWebJob for MyWebSite

## PARAMETERS

### -Force
Indicates that this cmdlet removes the web job without prompting you for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -JobType
The web job type.
Can be 'triggered' or 'continuous'

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Triggered, Continuous

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
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

[Remove-AzureWebsite](3997c3b8-37ce-4135-a17d-63ae3bdd8e74)

[Get-AzureWebsiteJob](5ef76b84-385f-419e-8aba-228d53ce2232)

[New-AzureWebsiteJob](89c77daa-24fd-4b27-b624-3486fe642722)

[Start-AzureWebsiteJob](33bc54a9-76a7-45cd-92d5-662e16354fa3)

[Stop-AzureWebsiteJob](9698753f-0bfc-4845-b74e-6c6bed38a430)

