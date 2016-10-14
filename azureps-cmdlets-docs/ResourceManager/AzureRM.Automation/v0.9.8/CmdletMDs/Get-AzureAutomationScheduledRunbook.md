---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Register-AzureAutomationScheduledRunbook.md
schema: 2.0.0
---

# Get-AzureAutomationScheduledRunbook

## SYNOPSIS
Gets Automation runbooks and associated schedules.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByJobScheduleId
```
Get-AzureAutomationScheduledRunbook -JobScheduleId <Guid> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByRunbookNameAndScheduleName
```
Get-AzureAutomationScheduledRunbook -RunbookName <String> -ScheduleName <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByRunbookName
```
Get-AzureAutomationScheduledRunbook -RunbookName <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByScheduleName
```
Get-AzureAutomationScheduledRunbook -ScheduleName <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationScheduledRunbook** gets one or more Azure Automation runbooks and associated schedules.
By default, this cmdlet gets all scheduled runboooks.
Specify the name of a runbook or a schedule or both to see specific runbook schedules.

## EXAMPLES

### Example 1: Get all scheduled runbooks
```
PS C:\>Get-AzureAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01"
```

This command gets all scheduled runbooks in the Azure Automation account named Contoso17.

### Example 2: Get all schedules associated with a runbook
```
PS C:\>Get-AzureAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -RunbookName "Runbk01"
```

This command gets all scheduled runbooks for the runbook Runbk01 in the Azure Automation account named Contoso17.

### Example 3: Get all runbooks associated with a schedule
```
PS C:\>Get-AzureAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -ScheduleName "Schedule01"
```

This command gets all scheduled runbooks for the schedule Schedule01 in the Azure Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies an Automation account for the runbook on which this cmdlet operates.

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

### -JobScheduleId
Specifies the ID of a scheduled job that this cmdlet gets.

```yaml
Type: Guid
Parameter Sets: ByJobScheduleId
Aliases: 

Required: True
Position: Named
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

### -RunbookName
Specifies the name of a runbook for which this cmdlet gets scheduled runbooks.

```yaml
Type: String
Parameter Sets: ByRunbookNameAndScheduleName, ByRunbookName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleName
Specifies the name of a schedule for which this cmdlet gets scheduled runbooks.

```yaml
Type: String
Parameter Sets: ByRunbookNameAndScheduleName, ByScheduleName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.JobSchedule

## NOTES

## RELATED LINKS

[Register-AzureAutomationScheduledRunbook](.\Register-AzureAutomationScheduledRunbook.md)

[Unregister-AzureAutomationScheduledRunbook](.\Unregister-AzureAutomationScheduledRunbook.md)

