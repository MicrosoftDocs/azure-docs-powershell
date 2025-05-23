---
external help file: Az.BotService-help.xml
Module Name: Az.BotService
online version: https://learn.microsoft.com/powershell/module/az.botservice/export-azbotserviceapp
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/BotService/BotService/help/Export-AzBotServiceApp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/BotService/BotService/help/Export-AzBotServiceApp.md
---

# Export-AzBotServiceApp

## SYNOPSIS
Returns a BotService specified by the parameters.

## SYNTAX

```
Export-AzBotServiceApp [-ResourceGroupName <String>] [-Name <String>] [-SavePath <String>]
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Returns a BotService specified by the parameters.

## EXAMPLES

### Example 1: Download the BotService App folder
```powershell
Export-AzBotServiceApp -ResourceGroupName youriBotTest -name youriechobottest
```

```output
Parameter $SavePath not provided, defaulting to current working directory.

    Directory: D:\powershell\BotService\azure-powershell\src\BotService

Mode                   LastWriteTime          Length Name
----                   -------------          ------ ----
d----          2020/12/15    1:45 PM                 youriechobottest
```

Download the BotService App folder

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the Bot resource.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: BotName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the Bot resource group in the user subscription.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SavePath

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Azure Subscription ID.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.BotService.Models.IBot

## NOTES

## RELATED LINKS
