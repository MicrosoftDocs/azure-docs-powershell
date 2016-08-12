---
external help file: RMAzure_Automation.xml
online version: 614eee0d-f18e-4843-bed6-6cf43db59f75
schema: 2.0.0
---

# Import-AzureRMAutomationRunbook
## SYNOPSIS
Imports an Automation runbook.

## SYNTAX

```
Import-AzureRMAutomationRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Path] <String> [-Description <String>] [-Force] [-LogProgress <Boolean]>] [-LogVerbose <Boolean]>]
 [-Name <System.String>] [-Published] [-Tags <IDictionary>] [-Type] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Import-AzureRmAutomationRunbook** cmdlet imports an azure_2 Automation runbook.
Specify the path to a wps_2 script (.ps1 ) file to import for wps_2 and wps_2 Workflow runbooks, or to a graphical runbook (.graphrunbook) file for graphical runbooks.
The name of the file becomes the name of the runbook.
For wps_2 Workflow runbooks, the script must contain a single wps_2 Workflow definition that matches the name of the file.

## EXAMPLES

### Example 1: Import a runbook from a file
```
PS C:\>$Tags = @{"tag01"='value01"; "tag02"="value02"}
PS C:\> Import-AzureRmAutomationRunbook -Path .\GraphicalRunbook06.graphrunbook -Tags $Tags -ResourceGroup "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -Type GraphicalPowershell
```

The first command assigns two key/value pairs to the $Tags variable.

The second command imports a graphical runbook called GraphicalRunbook06 into the Automation account named AutomationAccount01.
The command also assigns the tags stored in $Tags.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account into which this cmdlet imports a runbook.

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
Specifies a description for the imported runbook.

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

### -LogProgress
Specifies whether the runbook logs progress information.

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
Specifies whether the runbook logs detailed information.

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
Specifies the name of the runbook that this cmdlet imports.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RunbookName

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path of a .ps1 or .graphrunbook file that this cmdlet imports.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SourcePath

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Published
Indicates that this cmdlet publishes the runbook that it imports.

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

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet imports a runbook.

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
Specifies a dictionary of tags for the imported runbook.

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

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[New-AzureRmAutomationRunbook](c0de19b6-68a5-46b0-8575-88f229fd2494)

[Publish-AzureRmAutomationRunbook](68a3d64a-280b-4285-b588-72c7a8c25942)

[Remove-AzureRmAutomationRunbook](073fedf2-2bbd-4173-946a-b79f88dc3c92)

[Set-AzureRmAutomationRunbook](80b64633-ceab-4609-bb58-e11ab99e9c35)

[Start-AzureRmAutomationRunbook](5c86545a-93dd-4b3c-96b2-fa6ed740448d)

