---
external help file: RMAzure_Automation.xml
online version: 71da0434-5c0f-498f-91f2-f09117dfa7ca
schema: 2.0.0
---

# Export-AzureRMAutomationRunbook
## SYNOPSIS
Exports an Automation runbook.

## SYNTAX

```
Export-AzureRMAutomationRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Force] [-OutputFolder <String>] [-Slot] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Export-AzureRmAutomationRunbook** cmdlet exports an azure_2 Automation runbook to a wps_2 script (.ps1 ) file, for wps_2 or wps_2 Workflow runbooks, or to a graphical runbook (.graphrunbook) file, for graphical runbooks.
The name of the runbook becomes the name of the exported file.

## EXAMPLES

### Example 1: Export a runbook
```
PS C:\>Export-AzureRmAutomationRunbook -ResourceGroupName "ResourceGroup01" -AutomationAccountName "ContosoAutomationAccount" -Name "Runbook03" -Slot "Published" -OutputFolder "C:\Users\PattiFuller\Desktop"
```

This command exports the published version of an Automation runbook to a user desktop.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account in which this cmdlet exports a runbook.

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
ps_force

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
Specifies the name of the runbook that this cmdlet exports.
The name of the runbook becomes the name of the export file.

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

### -OutputFolder
Specifies the path of a folder in which this cmdlet creates the export file.

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

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet exports a runbook.

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

### -Slot
Specifies whether this cmdlet exports the draft or published content of the runbook.
Valid values are: 

-- Published 
-- Draft

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Published, Draft

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Get-AzureRmAutomationRunbook](71da0434-5c0f-498f-91f2-f09117dfa7ca)

[Import-AzureRmAutomationRunbook](6e05b8c0-5782-4580-b4e3-778e951be608)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[Publish-AzureRmAutomationRunbook](68a3d64a-280b-4285-b588-72c7a8c25942)

[Remove-AzureRmAutomationRunbook](073fedf2-2bbd-4173-946a-b79f88dc3c92)

[Set-AzureRmAutomationRunbook](80b64633-ceab-4609-bb58-e11ab99e9c35)

[Start-AzureRmAutomationRunbook](5c86545a-93dd-4b3c-96b2-fa6ed740448d)

