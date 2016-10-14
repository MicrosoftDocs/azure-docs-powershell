---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccountKeys.md
schema: 2.0.0
---

# Remove-AzureBatchJob

## SYNOPSIS
Deletes the specified Batch job.

## SYNTAX

```
Remove-AzureBatchJob [-Id] <String> [-Force] -BatchContext <BatchAccountContext> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureBatchJob** cmdlet deletes the specified Azure Batch job.
You will be prompted for confirmation unless you use the *Force* parameter.

## EXAMPLES

### Example 1: Delete a Batch job by id
```
PS C:\>Remove-AzureBatchJob -Id "Job-000001" -BatchContext $Context
```

This command deletes the job with ID Job-000001.
The user is prompted for confirmation before the delete operation takes place.

### Example 2: Delete a Batch job by pipelining without confirmation
```
PS C:\>Get-AzureBatchJob -Id "Job-000002" -BatchContext $Context | Remove-AzureBatchJob -Force -BatchContext $Context
```

This command deletes the job with ID Job-000002.
Since the *Force* parameter is present, the confirmation prompt is suppressed.

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
Specifies the ID of the job to delete.
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

[Get-AzureBatchAccountKeys](.\Get-AzureBatchAccountKeys.md)

[Get-AzureBatchJob](.\Get-AzureBatchJob.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

