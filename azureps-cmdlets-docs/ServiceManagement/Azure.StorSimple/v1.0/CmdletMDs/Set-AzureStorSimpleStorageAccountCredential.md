---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleStorageAccountCredential.md
schema: 2.0.0
---

# Set-AzureStorSimpleStorageAccountCredential

## SYNOPSIS
Updates an Azure storage access credential.

## SYNTAX

```
Set-AzureStorSimpleStorageAccountCredential [-StorageAccountName] <String> [[-StorageAccountKey] <String>]
 [[-UseSSL] <Boolean>] [-WaitForComplete] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureStorSimpleStorageAccountCredential** cmdlet update an existing Azure storage access credential for use by StorSimple OneSDK cmdlets.
For more information about how StorSimple cmdlets work with storage accounts, see the help topic for the New-AzureStorSimpleStorageAccountCredential cmdlet.

## EXAMPLES

### Example 1: Modify a credential
```
PS C:\>Set-AzureStorSimpleStorageAccountCredential -StorageAccountName "ContosoStorage01" -UseSSL $False -StorageAccountKey "h9ldH4LlHJB3GujcNwgdxJACy1DaQ1Hak1bfoUBzrDqZ5DPK8+0XGbsgD+jrKfQy5PBepKpYobMViLaOC2XMdg==" -Force -WaitForComplete
VERBOSE: ClientRequestId: 20cd2b17-9cff-4ab4-a034-96d60d946295_PS
VERBOSE: ClientRequestId: a75ed193-1da5-491f-96f5-572b5461d466_PS
VERBOSE: ClientRequestId: db612c9e-e89a-404f-8406-e66e7f697cd5_PS
VERBOSE: Storage credential verification succeeded. 
VERBOSE: Encryption in progress... 
VERBOSE: About to run a task to update your Storage Access credential! 
VERBOSE: ClientRequestId: a0995bb7-8223-4fcf-83c9-0a4f81e6a85c_PS


JobId        : 74a6172e-d47a-4824-a7fa-3eb207a76e0b
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {}

VERBOSE: The job created for your update operation has completed successfully. 
VERBOSE: ClientRequestId: de04c77b-4846-45e0-9257-df501af9d4e9_PS
CloudType                        : Azure
Hostname                         : blob.core.windows.net
InstanceId                       : 8b3cb7bb-963b-4173-9598-52fe230b0350
IsDefault                        : False
Location                         : West US
Login                            : ContosoStorage01
Name                             : ContosoStorage01
OperationInProgress              : None
Password                         : UUejow8u6ZynMm18g59883FBVtlIX6PWh6x+v15cnnkHKEAb5queTGnGOiGa/KkOqths7F/umDz+wUUB8zzq
                                   4YCi0Dm0rqPGDC4unhxvbncf+WeCEvV7qsf3pmUFdk8o96Cgl8oXgmmvYL9K6Z6ajHUdZFFlq9WqUpz2vBbz
                                   3ROxq8SRORt2DQVQP6LWojTiow1kNI/v2cs3eNvzoSgGftqzjSmhaTYu+q0o8X07eE4KwkWhQrRX24seH2Lg
                                   N9aYCQUrSxVKOAFJjdLOIBUlM48pnE7xyyZNwqngnPLt8z+mlS6JCKfo5SBKUfwmkhgDFfbVwB3jqC/sV/G6
                                   omwQ/A==
PasswordEncryptionCertThumbprint : 
UseSSL                           : False
VolumeCount                      : 0
```

This command changes the storage account credential named ContosoStorage01 to no longer require SSL.

## PARAMETERS

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

### -StorageAccountKey
Specifies the access key of the storage account in plain text.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Key

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the name of an existing storage account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL
Indicates whether to use SSL for the connection when using the new storage account credential.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### StorageAccountCredentialResponse, TaskResponse
This cmdlet returns a **StorageAccountCredentialResponse** object, if you specify the *WaitForComplete* parameter.
If you do not specify that parameter, the cmdlet returns a **TaskResponse** object.
A **StorageAccountCredentialResponse** contains the following properties: 

- **CloudType** (**CloudType**)
- **Hostname** (**String**)
- **InstanceId** (**String**)
- **IsDefault** (**Boolean**)
- **Location** (**String**)
- **Login** (**String**)
- **Name** (**String**)
- **OperationInProgress** (**OperationInProgress**)
- **Password** (**String**)
- **PasswordEncryptionCertThumbprint** (**String**)
- **UseSSL** (**Boolean**)
- **VolumeCount** (**int**)

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleStorageAccountCredential](.\Get-AzureStorSimpleStorageAccountCredential.md)

[New-AzureStorSimpleStorageAccountCredential](.\New-AzureStorSimpleStorageAccountCredential.md)

[Remove-AzureStorSimpleStorageAccountCredential](.\Remove-AzureStorSimpleStorageAccountCredential.md)

