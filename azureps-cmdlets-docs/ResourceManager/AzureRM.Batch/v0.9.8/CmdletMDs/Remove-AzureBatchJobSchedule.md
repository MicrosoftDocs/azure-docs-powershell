---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchJobSchedule.md
schema: 2.0.0
---

# Remove-AzureBatchJobSchedule

## SYNOPSIS
Removes a Batch job schedule.

## SYNTAX

```
Remove-AzureBatchJobSchedule [-Id] <String> [-Force] -BatchContext <BatchAccountContext>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureBatchJobSchedule** cmdlet removes an Azure Batch job schedule.
This cmdlet prompts you for confirmation before it removes a schedule.

## EXAMPLES

### Example 1: Delete a job schedule
```
PS C:\>Remove-AzureBatchJobSchedule "JobSchedule17" -BatchContext $Context
```

This command deletes the job schedule that has the ID JobSchedule17.
Use the **Get-AzureBatchAccountKeys** cmdlet to assign a context to the $Context variable.
This command prompts you before it removes the schedule.

### Example 2: Delete a job schedule without confirmation
```
PS C:\>Get-AzureBatchJobSchedule -Id "JobSchedule23" -BatchContext $Context | Remove-AzureBatchJobSchedule -Force -BatchContext $Context
```

This command gets the job schedule that has the ID JobSchedule23 by using the Get-AzureBatchJobSchedule cmdlet.
The command passes that schedule to the current cmdlet by using the pipeline operator.
The command removes that schedule.
The command specifies the *Force* parameter.
Therefore, it does not prompt you for confirmation.

## PARAMETERS

### -BatchContext
Specifies the **BatchAccountContext** instance that this cmdlet uses to interact with the Batch service.
To obtain a **BatchAccountContext** object that contains access keys for your subscription, use the Get-AzureBatchAccountKeys cmdlet.

```yaml
Type: BatchAccountContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -Id
Specifies the ID of the job schedule that this cmdlet removes.
You cannot specify wildcard characters.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureBatchJobSchedule](.\Get-AzureBatchJobSchedule.md)

[New-AzureBatchJobSchedule](.\New-AzureBatchJobSchedule.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

