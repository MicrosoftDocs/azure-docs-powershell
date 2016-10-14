---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Export-AzureAutomationRunbook.md
schema: 2.0.0
---

# Get-AzureAutomationRunbook

## SYNOPSIS
Gets a runbook.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByRunbookName
```
Get-AzureAutomationRunbook [-Name] <String> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationRunbook** cmdlet gets Azure Automation runbooks.
To get a specific runbook, specify its name.

## EXAMPLES

### Example 1: Get all runbooks
```
PS C:\>Get-AzureAutomationRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01"
```

This command gets all runbooks in the Azure Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account in which this cmdlet gets runbooks.

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
Specifies the name of a runbook that this cmdlet gets.

```yaml
Type: String
Parameter Sets: ByRunbookName
Aliases: RunbookName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group name.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Runbook

## NOTES

## RELATED LINKS

[Export-AzureAutomationRunbook](.\Export-AzureAutomationRunbook.md)

[Import-AzureAutomationRunbook](.\Import-AzureAutomationRunbook.md)

[New-AzureAutomationRunbook](.\New-AzureAutomationRunbook.md)

[Publish-AzureAutomationRunbook](.\Publish-AzureAutomationRunbook.md)

[Remove-AzureAutomationRunbook](.\Remove-AzureAutomationRunbook.md)

[Set-AzureAutomationRunbook](.\Set-AzureAutomationRunbook.md)

[Start-AzureAutomationRunbook](.\Start-AzureAutomationRunbook.md)

