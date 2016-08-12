---
external help file: SMAzure_Compute.xml
online version: 498c1abd-298b-43e9-ac53-bc57054a5387
schema: 2.0.0
---

# New-AzureWebsiteJob
## SYNOPSIS
Creates new web job for a website

## SYNTAX

```
New-AzureWebsiteJob [[-Name] <String>] [-Slot <String>] -JobFile <String> -JobName <String> [-JobType]
```

## DESCRIPTION
Creates new web job for a website

## EXAMPLES

### --------------  Create new web job for a website --------------
```
C:\PS>New-AzureWebsiteJob -Name MyWebsite -JobName MyWebJob -JobType Continuous -JobFile job.bat
```

Creates a continuous job to call job.bat on website MyWebsite

## PARAMETERS

### -JobFile
The web job file

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

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Get-AzureWebsiteJob](5ef76b84-385f-419e-8aba-228d53ce2232)

[Remove-AzureWebsiteJob](e25091a2-2472-4674-978c-ec1522631bc1)

[Start-AzureWebsiteJob](33bc54a9-76a7-45cd-92d5-662e16354fa3)

[Stop-AzureWebsiteJob](9698753f-0bfc-4845-b74e-6c6bed38a430)

