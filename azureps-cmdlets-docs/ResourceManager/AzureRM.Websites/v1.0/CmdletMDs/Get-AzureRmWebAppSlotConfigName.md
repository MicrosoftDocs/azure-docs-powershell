---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version: 472d30e3-a03c-4bde-b0fa-0c582ab8d88f
schema: 2.0.0
---

# Get-AzureRmWebAppSlotConfigName

## SYNOPSIS
Get the list of Web App Slot Config names

## SYNTAX

### S1
```
Get-AzureRmWebAppSlotConfigName [-ResourceGroupName] <String> [-Name] <String> [<CommonParameters>]
```

### S2
```
Get-AzureRmWebAppSlotConfigName [-WebApp] <Site> [<CommonParameters>]
```

## DESCRIPTION
The cmdlet retrieves the list of App Setting and Connection String names that are currently marked as slot settings

## EXAMPLES

### 1:
```
PS C:\>
```

## PARAMETERS

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

