---
external help file: RMAzure_Automation.xml
online version: 0bfb6a70-3a4a-4e58-a0b9-e41eb52a90ef
schema: 2.0.0
---

# Export-AzureRmAutomationDscNodeReportContent
## SYNOPSIS
Exports the raw content of a DSC report sent from a DSC node to Automation.

## SYNTAX

```
Export-AzureRmAutomationDscNodeReportContent [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Force] [-OutputFolder <String>] -NodeId <Guid> -ReportId <Guid> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Export-AzureRmAutomationDscNodeReportContent** cmdlet exports the raw contents of an APS Desired State Configuration (DSC) report.
A DSC node sends a DSC report to azure_2 Automation.

## EXAMPLES

### Example 1: Export a report from a DSC node
```
PS C:\>$Node = Get-AzureRmAutomationDscNode -ResourceGroupName "ResourceGroup03" -AutomationAccountName "AutomationAccount01" -Name "Computer14"
PS C:\> $Report = Get-AzureRmAutomationDscNodeReport -ResourceGroupName "ResourceGroup03" -AutomationAccountName "ContosoAutomationAccount" -NodeId $Node.Id -Latest
PS C:\> $Report | Export-AzureRmAutomationDscNodeReportContent -OutputFolder "C:\Users\PattiFuller\Desktop"
```

This set of commands exports the latest report from the DSC node named Computer14 to the desktop.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account.
This cmdlet exports report content for a DSC node that belongs to the Automation account that this parameter specifies.

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

### -Force
Indicates that this cmdlet replaces an existing local file with a new file that has the same name.

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

### -NodeId
Specifies the unique ID of the DSC node for which this cmdlet exports report contents.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -OutputFolder
Specifies the output folder where this cmdlet exports report contents.

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

### -ReportId
Specifies the unique ID of the DSC node report that this cmdlet exports.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group.
This cmdlet exports the contents of a report for the DSC node that belongs to the resource group that this cmdlet specifies.

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

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Export-AzureRmAutomationDscNodeReportContent](0bfb6a70-3a4a-4e58-a0b9-e41eb52a90ef)

[Get-AzureRmAutomationDscNode](19472f94-5827-4878-a17a-d7bb10932861)

[Get-AzureRmAutomationDscNodeReport](4e614479-d8a1-41bb-a8eb-8d833a314b54)

