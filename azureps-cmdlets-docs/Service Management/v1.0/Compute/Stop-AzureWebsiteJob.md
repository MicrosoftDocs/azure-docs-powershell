---
external help file: SMAzure_Compute.xml
online version: 62c5de93-e58b-4e57-85d0-8b7e75df1f31
schema: 2.0.0
---

# Stop-AzureWebsiteJob
## SYNOPSIS
Stops a web job for a website

## SYNTAX

```
Stop-AzureWebsiteJob [[-Name] <String>] [-PassThru] [-Slot <String>] -JobName <String>
```

## DESCRIPTION
Stops a web job for a website

## EXAMPLES

### --------------  Stop a web job for a website --------------
```
C:\PS>Stop-AzureWebsiteJob -Name MyWebsite -JobName MyWebJob -JobType Continuous
```

Stops a web job called MyWebJob for MyWebSite

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
Returns a boolean value indicating that the job stopped successfully.
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

[Stop-AzureWebsite](62c5de93-e58b-4e57-85d0-8b7e75df1f31)

[Get-AzureWebsiteJob](5ef76b84-385f-419e-8aba-228d53ce2232)

[New-AzureWebsiteJob](89c77daa-24fd-4b27-b624-3486fe642722)

[Remove-AzureWebsiteJob](e25091a2-2472-4674-978c-ec1522631bc1)

[Start-AzureWebsiteJob](33bc54a9-76a7-45cd-92d5-662e16354fa3)

