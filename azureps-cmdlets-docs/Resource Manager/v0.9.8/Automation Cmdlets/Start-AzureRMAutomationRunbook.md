---
external help file: RMAzure_Automation.xml
online version: 614eee0d-f18e-4843-bed6-6cf43db59f75
schema: 2.0.0
---

# Start-AzureRMAutomationRunbook
## SYNOPSIS
Starts a runbook job.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-AzureRMAutomationRunbook [-ResourceGroupName] <System.String> [-AutomationAccountName] <System.String>
 [-Name] <System.String> [-Parameters <System.Collections.IDictionary>] [-RunOn <System.String>]
```

### UNNAMED_PARAMETER_SET_2
```
Start-AzureRMAutomationRunbook [-ResourceGroupName] <System.String> [-AutomationAccountName] <System.String>
 [-Name] <System.String> [-MaxWaitSeconds <System.Int32>] [-Parameters <System.Collections.IDictionary>]
 [-RunOn <System.String>] [-Wait]
```

## DESCRIPTION
The **Start-AzureRmAutomationRunbook** cmdlet starts an azure_2 Automation runbook job.
Specify the ID or name of a runbook.

## EXAMPLES

### Example 1: Start a runbook job
```
PS C:\>Start-AzureRmAutomationRunbook -AutomationAccountName "Contoso17" -Name "Runbk01" -ResourceGroupName "ResourceGroup01"
```

This command starts a runbook job for the runbook named Runbk01 in the Azure Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
@{Text=}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -MaxWaitSeconds
@{Text=}

```yaml
Type: System.Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Type: System.String
Parameter Sets: (All)
Aliases: RunbookName

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Parameters
@{Text=}

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
@{Text=}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -RunOn
@{Text=}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HybridWorker

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Wait
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Job

## NOTES

## RELATED LINKS

[Export-AzureRmAutomationRunbook](614eee0d-f18e-4843-bed6-6cf43db59f75)

[Get-AzureRmAutomationRunbook](71da0434-5c0f-498f-91f2-f09117dfa7ca)

[Import-AzureRmAutomationRunbook](6e05b8c0-5782-4580-b4e3-778e951be608)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[Publish-AzureRmAutomationRunbook](68a3d64a-280b-4285-b588-72c7a8c25942)

[Remove-AzureRmAutomationRunbook](073fedf2-2bbd-4173-946a-b79f88dc3c92)

[Set-AzureRmAutomationRunbook](80b64633-ceab-4609-bb58-e11ab99e9c35)

