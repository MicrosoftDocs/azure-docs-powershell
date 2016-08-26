---
external help file: RMAzure_Automation.xml
online version: 614eee0d-f18e-4843-bed6-6cf43db59f75
schema: 2.0.0
---

# New-AzureRMAutomationRunbook
## SYNOPSIS
Creates an Automation runbook.

## SYNTAX

```
New-AzureRMAutomationRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Name] <String>
 [-Description <String>] [-LogProgress <Boolean]>] [-LogVerbose <Boolean]>] [-Tags <IDictionary>] [-Type]
```

## DESCRIPTION
The **New-AzureRmAutomationRunbook** cmdlet creates an empty azure_2 Automation runbook by using APS.
Specify a name for the runbook.

## EXAMPLES

### Example 1: Create a runbook
```
PS C:\>New-AzureRmAutomationRunbook -AutomationAccountName "Contoso17" -Name "Runbook02" -ResourceGroupName "ResourceGroup01"
```

This command creates a runbook named Runbook02 in the azure_2 Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account in which this cmdlet creates a runbook.

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

### -Description
Specifies a description for the runbook.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -LogProgress
Specifies whether the runbook logs progress.

```yaml
Type: Boolean]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -LogVerbose
Specifies whether logging includes detailed information.

```yaml
Type: Boolean]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the runbook.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RunbookName

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet creates a runbook.

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

### -Tags
Specifies a dictionary of tags for the new runbook.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Type
Specifies the type of runbook that this cmdlet creates.
Valid values are: 

-- PowerShell
-- GraphicalPowerShell
-- PowerShellWorkflow
-- GraphicalPowerShellWorkflow
-- Graph 

The value Graph is obsolete.
It is equivalent to GraphicalPowerShellWorkflow.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: PowerShell, GraphicalPowerShell, PowerShellWorkflow, GraphicalPowerShellWorkflow, Graph

Required: True
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

[Publish-AzureRmAutomationRunbook](68a3d64a-280b-4285-b588-72c7a8c25942)

[Remove-AzureRmAutomationRunbook](073fedf2-2bbd-4173-946a-b79f88dc3c92)

[Set-AzureRmAutomationRunbook](80b64633-ceab-4609-bb58-e11ab99e9c35)

[Start-AzureRmAutomationRunbook](5c86545a-93dd-4b3c-96b2-fa6ed740448d)

