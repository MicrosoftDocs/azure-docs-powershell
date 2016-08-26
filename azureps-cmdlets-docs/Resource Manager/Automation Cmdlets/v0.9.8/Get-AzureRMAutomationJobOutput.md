---
external help file: RMAzure_Automation.xml
online version: e41c8823-9e6a-4535-b90c-0e2de7634c47
schema: 2.0.0
---

# Get-AzureRMAutomationJobOutput
## SYNOPSIS
Gets the output of an Automation job.

## SYNTAX

```
Get-AzureRMAutomationJobOutput [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Id] <Guid>
 [-StartTime <DateTimeOffset]>] [-Stream]
```

## DESCRIPTION
The **Get-AzureRmAutomationJobOutput** cmdlet gets the output of an azure_2 Automation job.

## EXAMPLES

### Example 1: Get the output of an Automation job
```
PS C:\>Get-AzureRmAutomationJobOutput -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b64 -ResourceGroupName "ResourceGroup01" -Stream "Any"
```

This command gets all of the output of the job that has the specified ID.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account for which this cmdlet gets job output.

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

### -Id
Specifies the ID of a job for which this cmdlet gets output.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: JobId

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for which this cmdlet gets job output.

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
Specifies a start time as a **DateTimeOffset** object.
You can specify a string that can be converted to a valid **DateTimeOffset**.
The cmdlet retrieves output created after this time.

```yaml
Type: DateTimeOffset]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Stream
Specifies the type of output.
Valid values are: 

-- Any
-- Debug
-- Error
-- Output
-- Progress
-- Verbose
-- Warning

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Any, Progress, Output, Warning, Error, Debug, Verbose

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationJob](e41c8823-9e6a-4535-b90c-0e2de7634c47)

[Resume-AzureRmAutomationJob](4b289017-5b98-45bc-87c4-86b08e1ac322)

[Stop-AzureRmAutomationJob](1b580598-1087-4a10-9bc3-747ec5d7604a)

[Suspend-AzureRmAutomationJob](cf05770c-fc18-4a31-beb9-4f8c1c39c285)

