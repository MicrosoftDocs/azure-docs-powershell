---
external help file: SMAzure_Compute.xml
online version: 0c2a5092-db45-4ce7-b39b-d1e499b4a867
schema: 2.0.0
---

# Get-AzureWebsiteJob
## SYNOPSIS
Gets the web jobs associated with a website

## SYNTAX

```
Get-AzureWebsiteJob [[-Name] <String>] [-JobName <String>] [-JobType <String>] [-Slot <String>]
```

## DESCRIPTION
Gets the web jobs associated with a website

## EXAMPLES

### --------------  Get specific web job info --------------
```
C:\PS>Get-AzureWebsiteJob -Name MyWebsite -JobName MyWebJob
```

Gets a web job called MyWebJob from MyWebsite production slot

### --------------  Get all web jobs for a website --------------
```
C:\PS>Get-AzureWebsiteJob -Name MyWebsite
```

Gets all web jobs associated with MyWebsite production slot

### --------------  Get all triggered web jobs --------------
```
C:\PS>Get-AzureWebsiteJob -Name MyWebsite -Slot staging -Type Triggered
```

Gets all triggered web jobs from staging slot of MyWebsite

## PARAMETERS

### -JobName
The web job name

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

### -JobType
The web job type.
Can be 'triggered' or 'continuous'

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

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

[New-AzureWebsiteJob](89c77daa-24fd-4b27-b624-3486fe642722)

[Remove-AzureWebsiteJob](e25091a2-2472-4674-978c-ec1522631bc1)

[Start-AzureWebsiteJob](33bc54a9-76a7-45cd-92d5-662e16354fa3)

[Stop-AzureWebsiteJob](9698753f-0bfc-4845-b74e-6c6bed38a430)

