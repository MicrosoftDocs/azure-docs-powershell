---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: A2CBF963-1FAE-41B0-964E-EFF52076AB32
online version: 
schema: 2.0.0
---

# Get-AzureWebsiteJobHistory

## SYNOPSIS
Gets a web job history.

## SYNTAX

### HistoryParameterSetName
```
Get-AzureWebsiteJobHistory -JobName <String> [-Name <String>] [-Slot <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### RunIdParameterSetName
```
Get-AzureWebsiteJobHistory -JobName <String> -RunId <String> [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### LatestParameterSetName
```
Get-AzureWebsiteJobHistory -JobName <String> [-Latest] [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Gets a web job history.

## EXAMPLES

### Example 1: Get complete history for a web job
```
PS C:\> Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob
```

Gets complete history for MyWebJob.

### Example 2: Get latest run for a web job
```
PS C:\> Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob -Latest
```

Gets latest run info for MyWebJob.

### Example 3: Get specific run for a web job
```
PS C:\> Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob -RunId 10
```

Gets all info about run with id 10 for MyWebJob.

## PARAMETERS

### -JobName
The web job name.

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

### -Latest
If specified, return the latest run history.

```yaml
Type: SwitchParameter
Parameter Sets: LatestParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the Azure website.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunId
Specifies the ID of the run history you want to see.

```yaml
Type: String
Parameter Sets: RunIdParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
The slot name of the Azure website.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureWebsite](./Get-AzureWebsite.md)

[New-AzureWebsite](./New-AzureWebsite.md)

[Get-AzureWebsiteJob](./Get-AzureWebsiteJob.md)

[New-AzureWebsiteJob](./New-AzureWebsiteJob.md)

[Remove-AzureWebsiteJob](./Remove-AzureWebsiteJob.md)


