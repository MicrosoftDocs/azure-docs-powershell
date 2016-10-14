---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: .\Start-AzureWebsite.md
schema: 2.0.0
---

# Start-AzureWebsiteJob

## SYNOPSIS
Starts a web job for a website

## SYNTAX

```
Start-AzureWebsiteJob -JobName <String> -JobType <WebJobType> [-PassThru] [[-Name] <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
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

### -Name
The name of the Azure website

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
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
Default value: None
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
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobType
The web job type.
Can be 'triggered' or 'continuous'

```yaml
Type: WebJobType
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-AzureWebsite](.\Start-AzureWebsite.md)

[Get-AzureWebsiteJob](.\Get-AzureWebsiteJob.md)

[New-AzureWebsiteJob](.\New-AzureWebsiteJob.md)

[Remove-AzureWebsiteJob](.\Remove-AzureWebsiteJob.md)

[Start-AzureWebsiteJob](.\Start-AzureWebsiteJob.md)

