---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleStorageAccountCredential.md
schema: 2.0.0
---

# Remove-AzureStorSimpleStorageAccountCredential

## SYNOPSIS
Deletes an existing storage account credential.

## SYNTAX

### IdentifyByName
```
Remove-AzureStorSimpleStorageAccountCredential [-StorageAccountName] <String> [-WaitForComplete] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Remove-AzureStorSimpleStorageAccountCredential [-SAC] <StorageAccountCredentialResponse> [-WaitForComplete]
 [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureStorSimpleStorageAccountCredential** cmdlet deletes an existing storage account credential.
Specify an account by name or use the **Get-AzureStorSimpleStorageAccountCredential** cmdlet to obtain a **StorageAccountCredential** object to delete.

## EXAMPLES

### Example 1: Remove a storage account credential
```
PS C:\>Remove-AzureStorSimpleStorageAccountCredential -StorageAccountName "ContosoStorage07" -Force
VERBOSE: ClientRequestId: 8e10d56b-ddb1-459b-b26e-a185f5a303de_PS
VERBOSE: About to create a job to remove your Storage Access Credential! 
VERBOSE: ClientRequestId: 55cb6296-0156-4266-8591-d9e9bf8cc584_PS
982f4b19-ccb0-4ad3-9b02-f8ad25bf2e72
VERBOSE: The delete task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
982f4b19-ccb0-4ad3-9b02-f8ad25bf2e72 for tracking the task's status
```

This command removes the account credential for the storage account named ContosoStorage07.
This command specifies the *Force* parameter.
The cmdlet removes the credential without prompting your for confirmation.

### Example 2: Remove a storage account credential by using the pipeline operator
```
PS C:\>Get-AzureStorSimpleStorageAccountCredential -StorageAccountName "ContosoStorage07" | Remove-AzureStorSimpleStorageAccountCredential -Force -WaitForComplete
VERBOSE: ClientRequestId: f1b46216-bf4c-4c19-8e92-1dfe3894e258_PS
VERBOSE: ClientRequestId: 0d946f8f-c771-4ade-8a83-7c08dad86c52_PS
VERBOSE: ClientRequestId: 2000bab6-8311-4192-ad12-c67e35fc2697_PS
VERBOSE: Storage Access Credential with name ContosoStorage07 found! 
VERBOSE: About to run a job to remove your Storage Access Credential! 
VERBOSE: ClientRequestId: b803b165-bef8-4a8f-9509-4b515ea8bdec_PS
VERBOSE: Your delete operation completed successfully!
```

This command gets the storage account named ContosoStorage07 by using the **Get-AzureStorSimpleStorageAccountCredential** cmdlet, and then passes that object to the current cmdlet.
The current cmdlet removes the credential for that storage account.
This command specifies the *WaitForComplete* parameter.
The cmdlet does not return control to the console until it completes the remove operation.

## PARAMETERS

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
Specifies an azure_2 profile.

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

### -SAC
Specifies credential, as a **StorageAccountCredential** object, to remove.
To obtain a **StorageAccountCredential** object, use the **Get-AzureStorSimpleStorageAccountCredential** cmdlet.

```yaml
Type: StorageAccountCredentialResponse
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the name of the storage account credential to delete.

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

### -WaitForComplete
Indicates that this cmdlet waits for the operation to complete before it returns control to the wps_1 console.

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

### StorageAccountCredential
This cmdlet accepts a **StorageAccountCredential** object by using the pipeline.

## OUTPUTS

### TaskStatusInfo
This cmdlet returns a **TaskStatusInfo** object, if you specify the *WaitForComplete* parameter.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleStorageAccountCredential](.\Get-AzureStorSimpleStorageAccountCredential.md)

[New-AzureStorSimpleStorageAccountCredential](.\New-AzureStorSimpleStorageAccountCredential.md)

[Set-AzureStorSimpleStorageAccountCredential](.\Set-AzureStorSimpleStorageAccountCredential.md)

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

