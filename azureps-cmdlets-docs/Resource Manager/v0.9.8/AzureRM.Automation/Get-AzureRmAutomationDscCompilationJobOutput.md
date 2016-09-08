---
external help file: RMAzure_Automation.xml
online version: cbd50659-1e44-425c-9b97-a58be040e3b9
schema: 2.0.0
---

# Get-AzureRmAutomationDscCompilationJobOutput
## SYNOPSIS
Gets the logging streams of an Automation DSC compilation job.

## SYNTAX

```
Get-AzureRmAutomationDscCompilationJobOutput [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Id] <Guid> [-StartTime <DateTimeOffset]>] [-Stream]
```

## DESCRIPTION
The **Get-AzureRmAutomationDscCompilationJobOutput** cmdlet gets the stream records of an APS Desired State Configuration (DSC) compilation job in azure_2 Automation.

## EXAMPLES

### Example 1: Get the logs for a DSC compilation job
```
PS C:\>$Jobs = Get-AzureRmAutomationDscCompilationJob -ResourceGroupName "ResourceGroup01" -AutomationAccountName "Contoso17"
PS C:\> $Jobs[0] | Get-AzureRmAutomationDscCompilationJobOutput -Stream "Any"
```

The first command gets the compilation jobs in the Automation account named Contoso17 by using the Get-AzureRmAutomationDscCompilationJob cmdlet.
The command stores those objects in the $Jobs variable.

The second command gets the compilation job output for any stream for the first member of the $Jobs array.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account that contains the DSC compilation job.

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
Specifies the unique ID of the DSC compilation job for which this cmdlet gets output.

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
Specifies the name of the resource group that contains the DSC compilation job for which this cmdlet gets stream records.

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
This cmdlet gets stream records that the DSC compilation job outputs after this time.

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
Specifies the type of stream for the output that this cmdlet gets.
Valid values are: 

-- Any 
-- Warning 
-- Error 
-- Verbose

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Any, Warning, Error, Verbose

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

[Get-AzureRmAutomationDscCompilationJob](cbd50659-1e44-425c-9b97-a58be040e3b9)

[Start-AzureRmAutomationDscCompilationJob](d1d461ab-138f-42f2-8faf-e651a8310b08)

