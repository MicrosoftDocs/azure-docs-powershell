---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=397910
schema: 2.0.0
ms.assetid: 5A7761DE-2D9C-4217-9B8D-6E38DAF2820F
---

# Publish-AzureAutomationRunbook

## SYNOPSIS
Publishes a runbook.

## SYNTAX

```
Publish-AzureAutomationRunbook [-Name] <String> [-AutomationAccountName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Publish-AzureAutomationRunbook** cmdlet publishes a runbook for use in the production environment of Microsoft Azure Automation.

## EXAMPLES

### Example 1: Publish a runbook
```
PS C:\>Publish-AzureAutomationRunbook -AutomationAccountName "Contoso17" -Name "Runbk01"
```

This command publishes the runbook named Runbk01 in the Azure Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: RunbookName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureProfile
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

[Get-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Get-AzureAutomationRunbook.md)

[New-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\New-AzureAutomationRunbook.md)

[Remove-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Remove-AzureAutomationRunbook.md)

[Set-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Set-AzureAutomationRunbook.md)

[Start-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Start-AzureAutomationRunbook.md)


