---
external help file: RMAzure_Automation.xml
online version: 614eee0d-f18e-4843-bed6-6cf43db59f75
schema: 2.0.0
---

# Get-AzureRMAutomationRunbook
## SYNOPSIS
Gets a runbook.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationRunbook** cmdlet gets azure_2 Automation runbooks.
To get a specific runbook, specify its name.

## EXAMPLES

### Example 1: Get all runbooks
```
PS C:\>Get-AzureRmAutomationRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01"
```

This command gets all runbooks in the azure_2 Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account in which this cmdlet gets runbooks.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a runbook that this cmdlet gets.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: RunbookName

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet gets runbooks.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Runbook

## NOTES

## RELATED LINKS

[Export-AzureRmAutomationRunbook](614eee0d-f18e-4843-bed6-6cf43db59f75)

[Import-AzureRmAutomationRunbook](6e05b8c0-5782-4580-b4e3-778e951be608)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[Publish-AzureRmAutomationRunbook](68a3d64a-280b-4285-b588-72c7a8c25942)

[Remove-AzureRmAutomationRunbook](073fedf2-2bbd-4173-946a-b79f88dc3c92)

[Set-AzureRmAutomationRunbook](80b64633-ceab-4609-bb58-e11ab99e9c35)

[Start-AzureRmAutomationRunbook](5c86545a-93dd-4b3c-96b2-fa6ed740448d)

