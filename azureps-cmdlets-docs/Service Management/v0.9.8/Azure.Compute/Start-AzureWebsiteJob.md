---
external help file: SMAzure_Compute.xml
online version: d6ee400f-4a92-4f2f-83bb-70188bb2000d
schema: 2.0.0
---

# Start-AzureWebsiteJob
## SYNOPSIS
Starts a web job for a website

## SYNTAX

```
Start-AzureWebsiteJob [[-Name] <String>] [-PassThru] [-Slot <String>] -JobName <String> [-JobType]
```

## DESCRIPTION
Starts a web job for a website

## EXAMPLES

### --------------  Start a web job for a website --------------
```
C:\PS>Start-AzureWebsiteJob -Name MyWebsite -JobName MyWebJob -JobType Continuous
```

Starts a web job called MyWebJob for MyWebSite

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

### -PassThru
Returns a boolean value indicating that the job started successfully.
By default, this cmdlet does not return any output.

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

[Start-AzureWebsite](d6ee400f-4a92-4f2f-83bb-70188bb2000d)

[Get-AzureWebsiteJob](5ef76b84-385f-419e-8aba-228d53ce2232)

[New-AzureWebsiteJob](89c77daa-24fd-4b27-b624-3486fe642722)

[Remove-AzureWebsiteJob](e25091a2-2472-4674-978c-ec1522631bc1)

[Start-AzureWebsiteJob](33bc54a9-76a7-45cd-92d5-662e16354fa3)

