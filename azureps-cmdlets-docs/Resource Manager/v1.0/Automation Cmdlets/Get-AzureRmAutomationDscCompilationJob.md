---
external help file: RMAzure_Automation.xml
online version: 0375f514-6679-4488-be72-816df6f13124
schema: 2.0.0
---

# Get-AzureRmAutomationDscCompilationJob
## SYNOPSIS
Gets DSC compilation jobs in Automation.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRmAutomationDscCompilationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-EndTime <DateTimeOffset]>] [-StartTime <DateTimeOffset]>] [-Status]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRmAutomationDscCompilationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 -Id <Guid>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureRmAutomationDscCompilationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-EndTime <DateTimeOffset]>] [-StartTime <DateTimeOffset]>] [-Status] -ConfigurationName <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationDscCompilationJob** cmdlet gets APS Desired State Configuration (DSC) compilation jobs in azure_2 Automation.

## EXAMPLES

### Example 1: Get all DSC compilation jobs
```
PS C:\>Get-AzureRmAutomationDscCompilationJob -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17"
```

This command gets all compilation jobs in the Automation account named Contoso17.

### Example 2: Get DSC compilation jobs for a configuration
```
PS C:\>Get-AzureRmAutomationDscCompilationJob -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -ConfigurationName "ContosoConfiguration"
```

This command gets all compilation jobs for the DSC configuration named ContosoConfiguration in the Automation account named Contoso17.

### Example 3: Get a specific DSC compilation job
```
PS C:\>Get-AzureRmAutomationDscCompilationJob -ResourceGroupName "ResourceGroup03" -AutomationAccountName "Contoso17" -Id c0a1718e-d8be-4fa3-91b6-82e1d3a36298
```

This command gets the compilation job with the specified ID in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains DSC compilation jobs that this cmdlet gets.

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

### -ConfigurationName
Specifies the name of the DSC configuration for which this cmdlet gets compilation jobs.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Specifies an end time.
This cmdlet gets compilations jobs that started up to the time that this parameter specifies.

```yaml
Type: DateTimeOffset]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the unique ID of the DSC compilation job that this cmdlet gets.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: JobId

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group in which this cmdlet gets DSC compilation jobs.

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

### -StartTime
Specifies a start time.
This cmdlet gets jobs that start at or after the time that this parameter specifies.

```yaml
Type: DateTimeOffset]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Specifies the status of jobs that this cmdlet gets.
Valid values are: 

-- Completed 
-- Failed 
-- Queued 
-- Starting 
-- Resuming 
-- Running 
-- Stopped 
-- Stopping 
-- Suspended 
-- Suspending 
-- Activating

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
Aliases: 
Accepted values: Completed, Failed, Queued, Starting, Resuming, Running, Stopped, Stopping, Suspended, Suspending, Activating

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationDscCompilationJobOutput](0375f514-6679-4488-be72-816df6f13124)

[Start-AzureRmAutomationDscCompilationJob](d1d461ab-138f-42f2-8faf-e651a8310b08)

