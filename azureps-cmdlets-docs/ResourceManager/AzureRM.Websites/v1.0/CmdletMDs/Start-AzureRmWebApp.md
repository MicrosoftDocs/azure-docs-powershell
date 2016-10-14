---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version: .\Get-AzureRmWebApp.md
schema: 2.0.0
---

# Start-AzureRmWebApp

## SYNOPSIS
Starts an azure_2 Web App.

## SYNTAX

### S1
```
Start-AzureRmWebApp [-ResourceGroupName] <String> [-Name] <String> [<CommonParameters>]
```

### S2
```
Start-AzureRmWebApp [-WebApp] <Site> [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureRmWebApp** cmdlet starts an azure_2 Web App.

## EXAMPLES

### Example 1: Start a Web App
```
PS C:\>Start-AzureRmWebApp -ResourceGroupName "Default-Web-WestUS" -Name "ContosoWebApp"
```

This command starts the Web App named ContosoWebApp that belongs to the resource group named Default-Web-WestUS.

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

[Get-AzureRmWebApp](.\Get-AzureRmWebApp.md)

[New-AzureRmWebApp](.\New-AzureRmWebApp.md)

[Remove-AzureRmWebApp](.\Remove-AzureRmWebApp.md)

[Restart-AzureRmWebApp](.\Restart-AzureRmWebApp.md)

[Stop-AzureRmWebApp](.\Stop-AzureRmWebApp.md)

