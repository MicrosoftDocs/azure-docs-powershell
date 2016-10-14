---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleAccessControlRecord.md
schema: 2.0.0
---

# Remove-AzureStorSimpleAccessControlRecord

## SYNOPSIS
Deletes an access control record from the service configuration.

## SYNTAX

### IdentifyByName
```
Remove-AzureStorSimpleAccessControlRecord [-ACRName] <String> [-WaitForComplete] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Remove-AzureStorSimpleAccessControlRecord [-ACR] <AccessControlRecord> [-WaitForComplete] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureStorSimpleAccessControlRecord** cmdlet deletes an access control record from the service configuration.

## EXAMPLES

### Example 1: Remove an Access Controlaccess control recordaccess control
```
PS C:\>Remove-AzureStorSimpleAccessControlRecord -ACRName "Acr10" -WaitForComplete -Force
VERBOSE: ClientRequestId: 574aeb7f-fbc9-46d5-bc68-1bfe4487bd8b_PS
VERBOSE: ClientRequestId: 985afe84-ef95-47cb-8c8f-df094530334b_PS
VERBOSE: About to run a job to remove your ACR! 
VERBOSE: ClientRequestId: 7eb7e1a0-2288-44da-b64c-5bf86a6b9aaf_PS


JobId        : f7934db5-8363-4152-b38e-b9a5d91f97b9
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {}

VERBOSE: The job created for your delete operation has completed successfully.
```

This command deletes the access control record named Acr10.
This command specifies the *WaitForComplete* parameter, and, therefore, the command waits until the operation is complete, and then returns a **TaskStatusInfo** object.

### Example 2: Remove an Access Controlaccess control record by using the pipelineAccess Controlaccess controlaccess control
```
PS C:\>Get-AzureStorSimpleAccessControlRecord -ACRName "Acr10" | Remove-AzureStorSimpleAccessControlRecord -Force 
VERBOSE: ClientRequestId: ff8d8bd6-4c92-4ab6-8fde-e9344a253da3_PS
VERBOSE: ClientRequestId: f71c74f3-33b9-40d1-b8d5-12363e98412f_PS
VERBOSE: ClientRequestId: d5d809d0-ec22-4e45-97ee-a56edc41e503_PS
VERBOSE: About to create a job to remove your ACR! 
VERBOSE: ClientRequestId: 6ffa6bc8-37b3-49ff-bafc-721b360f09cb_PS
294a0208-a43f-4d80-b824-2319cd77c5e6
VERBOSE: The delete task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
294a0208-a43f-4d80-b824-2319cd77c5e6 for tracking the task's status
```

This command uses the **Get-AzureStorSimpleAccessControlRecord** to get the **AccessControlRecord** named Acr10, and then passes that object to the current cmdlet by using the pipeline operator.
The command starts the operation that removes the **AccessControlRecord** object, and then returns a **TaskResponse** object.
To see the status of the task, use the **Get-AzureStorSimpleTask** cmdlet.

## PARAMETERS

### -ACR
Specifies an **AccessControlRecord** object to delete.
To obtain an **AccessControlRecord** object, use the **Get-AzureStorSimpleAccessControlRecord** cmdlet.

```yaml
Type: AccessControlRecord
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ACRName
Specifies a name of the access control record to delete.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet does not prompt you for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForComplete
Indicates that this cmdlet waits for the operation to complete before it returns control to the Windows PowerShell ‚Â® console.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### AccessControlRecord
This cmdlet accepts an **AccessControlRecord** object.
An **AccessControlRecord** object contains the following fields: 

- **GlobalId** (**String**) 
- **InitiatorName** (**String**) 
- **InstanceId** (**String**) 
- **Name** (**String**) 
- **OperationInProgress** (**OperationInProgress**) 
- **VolumeCount** (**int**)

## OUTPUTS

### TaskStatusInfo, TaskResponse
This cmdlet returns a **TaskStatusInfo** object if you specify the *WaitForComplete* parameter.
If you do not specify that parameter, it returns a **TaskResponse** object.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleAccessControlRecord](.\Get-AzureStorSimpleAccessControlRecord.md)

[New-AzureStorSimpleAccessControlRecord](.\New-AzureStorSimpleAccessControlRecord.md)

[Set-AzureStorSimpleAccessControlRecord](.\Set-AzureStorSimpleAccessControlRecord.md)

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

