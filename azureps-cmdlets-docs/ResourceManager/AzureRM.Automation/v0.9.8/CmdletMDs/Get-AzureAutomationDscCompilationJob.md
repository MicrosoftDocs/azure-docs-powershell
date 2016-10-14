---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\Start-AzureAutomationDscCompilationJob.md
schema: 2.0.0
---

# Get-AzureAutomationDscCompilationJob

## SYNOPSIS
Gets DSC compilation jobs in Automation.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationDscCompilationJob [-Status <String>] [-StartTime <DateTimeOffset>]
 [-EndTime <DateTimeOffset>] [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByJobId
```
Get-AzureAutomationDscCompilationJob -Id <Guid> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByConfigurationName
```
Get-AzureAutomationDscCompilationJob -ConfigurationName <String> [-Status <String>]
 [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>] [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationDscCompilationJob** cmdlet gets PowerShell Desired State Configuration (DSC) compilation jobs in Azure Automation.

## EXAMPLES

### Example 1: Get all DSC compilation jobs
```
PS C:\>Get-AzureAutomationDscCompilationJob -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17"
```

This command gets all compilation jobs in the Automation account named Contoso17.

### Example 2: Get DSC compilation jobs for a configuration
```
PS C:\>Get-AzureAutomationDscCompilationJob -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17" -ConfigurationName "MyConfiguration"
```

This command gets all compilation jobs for the DSC configuration named MyConfiguration in the Automation account named Contoso17.

### Example 3: Get a specific DSC compilation job
```
PS C:\>Get-AzureAutomationDscCompilationJob -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17" -Id 00000000-0000-0000-0000-000000000000
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationName
Specifies the name of the DSC configuration for which this cmdlet gets compilation jobs.

```yaml
Type: String
Parameter Sets: ByConfigurationName
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
Type: DateTimeOffset
Parameter Sets: ByAll, ByConfigurationName
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
Parameter Sets: ByJobId
Aliases: JobId

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
Specifies the name of a resource group in which this cmdlet gets DSC compilation jobs.

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

### -StartTime
Specifies a start time.
This cmdlet gets jobs that start at or after the time that this parameter specifies.

```yaml
Type: DateTimeOffset
Parameter Sets: ByAll, ByConfigurationName
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

- Completed 
- Failed 
- Queued 
- Starting 
- Resuming 
- Running 
- Stopped 
- Stopping 
- Suspended 
- Suspending 
- Activating

```yaml
Type: String
Parameter Sets: ByAll, ByConfigurationName
Aliases: 
Accepted values: Completed, Failed, Queued, Starting, Resuming, Running, Stopped, Stopping, Suspended, Suspending, Activating

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-AzureAutomationDscCompilationJob](.\Start-AzureAutomationDscCompilationJob.md)

[Get-AzureAutomationDscCompilationJobOutput](.\Get-AzureAutomationDscCompilationJobOutput.md)

