---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=397912
schema: 2.0.0
ms.assetid: 557C120E-D3FB-40CD-9CA3-DD27610E6DD7
---

# Remove-AzureAutomationRunbook

## SYNOPSIS
Removes a runbook.

## SYNTAX

```
Remove-AzureAutomationRunbook [-Name] <String> [-Force] [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureAutomationRunbook** cmdlet removes a runbook from Microsoft Azure Automation.

## EXAMPLES

### Example 1: Remove a runbook
```
PS C:\> Remove-AzureAutomationRunbook -AutomationAccountName "Contoso17" -Name "MyRunbook"
```

This command removes the runbook named MyRunbook in the Azure Automation account named Contoso17.

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

### -Force
@{Text=}

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

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

[Publish-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Publish-AzureAutomationRunbook.md)

[Set-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Set-AzureAutomationRunbook.md)

[Start-AzureAutomationRunbook](..\..\..\..\ResourceManager\AzureRM.Automation\v0.9.8\CmdletMDs\Start-AzureAutomationRunbook.md)


