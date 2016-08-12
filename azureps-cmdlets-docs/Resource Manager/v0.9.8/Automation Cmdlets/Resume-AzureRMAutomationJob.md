---
external help file: RMAzure_Automation.xml
online version: e41c8823-9e6a-4535-b90c-0e2de7634c47
schema: 2.0.0
---

# Resume-AzureRMAutomationJob
## SYNOPSIS
Resumes a suspended Automation job.

## SYNTAX

```
Resume-AzureRMAutomationJob [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-Id] <Guid>
```

## DESCRIPTION
The **Resume-AzureRmAutomationJob** cmdlet resumes a suspended azure_2 Automation job.
Specify the suspended job.

To suspend a job, use the Suspend-AzureRmAutomationJob cmdlet.

## EXAMPLES

### Example 1: Resume a suspended job
```
PS C:\>Resume-AzureRmAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b64 -ResourceGroupName "ResourceGroup01"
```

This command resumes the job that has the specified ID.

## PARAMETERS

### -AutomationAccountName
Specifies the name of an Automation account in which this cmdlet resume a job.

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
Specifies the ID of a job that this cmdlet resumes.

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
Specifies the name of a resource group for which this cmdlet resumes a job.

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

[Stop-AzureRmAutomationJob](1b580598-1087-4a10-9bc3-747ec5d7604a)

[Suspend-AzureRmAutomationJob](cf05770c-fc18-4a31-beb9-4f8c1c39c285)

