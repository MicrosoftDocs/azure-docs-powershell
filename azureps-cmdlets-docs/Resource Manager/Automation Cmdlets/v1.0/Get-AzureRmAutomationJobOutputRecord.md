---
external help file: RMAzure_Automation.xml
online version: 03d80a68-8443-42e0-87bc-5d0e22ac3a57
schema: 2.0.0
---

# Get-AzureRmAutomationJobOutputRecord
## SYNOPSIS
Gets the full output of an Automation job output record.

## SYNTAX

```
Get-AzureRmAutomationJobOutputRecord [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-JobId] <Guid> [-Id] <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationJobOutputRecord** cmdlet gets the full output of an Automation job output record.

Although the **Get-AzureRmAutomationJobOutput** cmdlet lists one or more job output records, it returns only a summary, as a string, of the value of any output record.
It does not return the full value of an output record's outputted value in its original type.
In addition, the summary has a maximum length, which the full value that this cmdlet outputs may exceed.
Unlike **Get-AzureRmAutomationJobOutput**, this cmdlet returns the full value in its originally outputted type, for any output record's outputted value.

## EXAMPLES

### Example 1: Get the full output of an Automation job
```
PS C:\>Get-AzureRmAutomationJobOutput -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b64 -ResourceGroupName "ResourceGroup01" -Stream "Any" | Get-AzureRmAutomationJobOutputRecord
```

This command gets the full output of the job that has the specified job ID.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account for which this cmdlet gets a job output record.

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
Specifies the ID of a job output record for this cmdlet to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StreamRecordId

Required: True
Position: 4
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -JobId
Specifies the ID of a job for which this cmdlet gets an output record.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group for which this cmdlet gets a job output record.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationJobOutput](03d80a68-8443-42e0-87bc-5d0e22ac3a57)

