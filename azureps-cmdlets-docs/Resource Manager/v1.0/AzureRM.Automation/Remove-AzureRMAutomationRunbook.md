---
external help file: RMAzure_Automation.xml
online version: 614eee0d-f18e-4843-bed6-6cf43db59f75
schema: 2.0.0
---

# Remove-AzureRMAutomationRunbook
## SYNOPSIS
Removes a runbook.

## SYNTAX

```
Remove-AzureRMAutomationRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureRmAutomationRunbook** cmdlet removes a runbook from azure_2 Automation.

## EXAMPLES

### Example 1: Remove a runbook
```
PS C:\>Remove-AzureRmAutomationRunbook -AutomationAccountName "Contoso17" -Name "Runbook03" -ResourceGroupName "ResourceGroup01"
```

This command removes the runbook named Runbook03 in the azure_2 Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account in which this cmdlet removes a runbook.

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
Specifies the name of the runbook that this cmdlet removes.

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
Specifies the name of the resource group for which this cmdlet publishes a runbook.

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

[Export-AzureRmAutomationRunbook](614eee0d-f18e-4843-bed6-6cf43db59f75)

[Get-AzureRmAutomationRunbook](71da0434-5c0f-498f-91f2-f09117dfa7ca)

[Import-AzureRmAutomationRunbook](6e05b8c0-5782-4580-b4e3-778e951be608)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[Publish-AzureRmAutomationRunbook](68a3d64a-280b-4285-b588-72c7a8c25942)

[Set-AzureRmAutomationRunbook](80b64633-ceab-4609-bb58-e11ab99e9c35)

[Start-AzureRmAutomationRunbook](5c86545a-93dd-4b3c-96b2-fa6ed740448d)

