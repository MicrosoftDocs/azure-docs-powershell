---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
ms.assetid: A4C605DD-9B2E-4EE9-BD1F-1352D605C33F
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/New-AzureRmActionGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/New-AzureRmActionGroup.md
gitcommit: https://github.com/Azure/azure-powershell/blob/bc68f11db3b16b8ed21d578a6edeb50312deedb0
---

# New-AzureRmActionGroup

## SYNOPSIS
Creates an ActionGroup reference object in memory.

## SYNTAX

```
New-AzureRmActionGroup -ActionGroupId <String> -WebhookProperties System.Collections.Generic.Dictionary`1[<string>, <string>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmActionGroup** cmdlet creates an action group reference object in memory.

## EXAMPLES

### Example 1: Create an action group reference object in memory
```
PS C:\>$dict = New-Object "System.Collections.Generic.Dictionary``2[System.String,System.String]"
PS C:\>$dict.Add('key1', 'value1')
PS C:\>$actionGrp1 = New-AzureRmActionGroup -ActionGroupId 'actiongr1' -WebhookProperties $dict
```

## PARAMETERS

### -ActionGroupId
The Id/name of the action group.

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

### -WebhookProperties
The dictionary of webhook properties, i.e. list of unique string, string pairs.

```yaml
Type: System.Collections.Generic.Dictionary`1[<string>, <string>]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertActionGroup

## NOTES

## RELATED LINKS

[Set-AzureRmActivityLogAlert](./Set-AzureRmActivityLogAlert.md)

[Enable-AzureRmActivityLogAlert](./Enable-AzureRmActivityLogAlert.md)

[Disable-AzureRmActivityLogAlert](./Disable-AzureRmActivityLogAlert.md)

[Get-AzureRmActivityLogAlert](./Get-AzureRmActivityLogAlert.md)

[Remove-AzureRmActivityLogAlert](./Remove-AzureRmActivityLogAlert.md)

[New-AzureRmActivityLogAlertCondition](./Get-AzureRmActivityLogAlertCondition.md)

