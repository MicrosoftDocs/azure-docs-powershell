---
external help file: RMAzure_Automation.xml
online version: e41c8823-9e6a-4535-b90c-0e2de7634c47
schema: 2.0.0
---

# Suspend-AzureRMAutomationJob
## SYNOPSIS
Suspends an Automation job.

## SYNTAX

```
Suspend-AzureRMAutomationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Id] <Guid>
```

## DESCRIPTION
The **Suspend-AzureRmAutomationJob** cmdlet suspends an azure_2 Automation job.
Specify a running Automation job.

To resume a suspended job, use the Resume-AzureRmAutomationJob cmdlet.

## EXAMPLES

### Example 1: Suspend a job
```
PS C:\>Suspend-AzureRmAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b64 -ResourceGroupName "ResourceGroup01"
```

This command suspends the job that has the specified ID.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account in which this cmdlet suspends a job.

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
Specifies the ID of a job that this cmdlet suspends.

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
Specifies the ID of a job that this cmdlet suspends.

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

[Get-AzureRmAutomationJob](e41c8823-9e6a-4535-b90c-0e2de7634c47)

[Get-AzureRmAutomationJobOutput](03d80a68-8443-42e0-87bc-5d0e22ac3a57)

[Resume-AzureRmAutomationJob](4b289017-5b98-45bc-87c4-86b08e1ac322)

[Stop-AzureRmAutomationJob](1b580598-1087-4a10-9bc3-747ec5d7604a)

