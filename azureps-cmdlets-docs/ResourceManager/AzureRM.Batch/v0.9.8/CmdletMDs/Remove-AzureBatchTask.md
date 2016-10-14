---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccountKeys.md
schema: 2.0.0
---

# Remove-AzureBatchTask

## SYNOPSIS
Deletes the specified Batch task.

## SYNTAX

### Id
```
Remove-AzureBatchTask [-JobId] <String> [-Id] <String> [-Force] -BatchContext <BatchAccountContext>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### InputObject
```
Remove-AzureBatchTask [-InputObject] <PSCloudTask> [-Force] -BatchContext <BatchAccountContext>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureBatchTask** cmdlet deletes the specified Azure Batch task.
You will be prompted for confirmation unless you use the *Force* parameter.

## EXAMPLES

### Example 1: Delete a Batch task by id with user confirmation
```
PS C:\>Remove-AzureBatchTask -JobId "Job-000001" -Id "MyTask" -BatchContext $Context
```

This command deletes the task with ID MyTask in job Job-000001.
The user is prompted for confirmation before the delete operation takes place.

### Example 2: Delete a Batch task by id without user confirmation
```
PS C:\>Get-AzureBatchTask "Job-000001" "MyTask2" -BatchContext $Context | Remove-AzureBatchTask -Force -BatchContext $Context
```

This command deletes the task with id MyTask2 in job Job-000001.
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
Specifies the ID of the task to delete.
You cannot specify wildcard characters.

```yaml
Type: String
Parameter Sets: Id
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the **PSCloudTask** object representing the task to delete.
Use the Get-AzureBatchTask cmdlet to get a **PSCloudTask** object.

```yaml
Type: PSCloudTask
Parameter Sets: InputObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Specifies the ID of the job containing the task to delete.

```yaml
Type: String
Parameter Sets: Id
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

[Get-AzureBatchTask](.\Get-AzureBatchTask.md)

[New-AzureBatchTask](.\New-AzureBatchTask.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

