---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version: .\Get-AzureRmAppServicePlan.md
schema: 2.0.0
---

# Get-AzureRmWebAppPublishingProfile

## SYNOPSIS
Gets an Azure Web App publishing profile.

## SYNTAX

### S1
```
Get-AzureRmWebAppPublishingProfile [-OutputFile] <String> [[-Format] <String>] [-ResourceGroupName] <String>
 [-Name] <String> [<CommonParameters>]
```

### S2
```
Get-AzureRmWebAppPublishingProfile [-OutputFile] <String> [[-Format] <String>] [-WebApp] <Site>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmWebAppPublishingProfile** cmdlet gets an Azure Web App publishing profile.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -OutputFile
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Format
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
@{Text=}

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
@{Text=}

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WebApp
@{Text=}

```yaml
Type: Site
Parameter Sets: S2
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAppServicePlan](.\Get-AzureRmAppServicePlan.md)

[Get-AzureRmWebApp](.\Get-AzureRmWebApp.md)

