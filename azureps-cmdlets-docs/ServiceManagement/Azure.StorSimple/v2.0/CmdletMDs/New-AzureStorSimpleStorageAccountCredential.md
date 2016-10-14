---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleStorageAccountCredential.md
schema: 2.0.0
---

# New-AzureStorSimpleStorageAccountCredential

## SYNOPSIS
Adds an Azure storage access credential.

## SYNTAX

```
New-AzureStorSimpleStorageAccountCredential [-StorageAccountName] <String> [-StorageAccountKey] <String>
 [-UseSSL] <Boolean> [[-Endpoint] <String>] [-WaitForComplete] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorSimpleStorageAccountCredential** cmdlet adds an Azure storage access credential to StorSimple manager for use by StorSimple OneSDK cmdlets.
Most of the StorSimple OneSDK cmdlets deal with entities that are eventually tied to a specific storage account, such as volumes, volume containers, backups, and backup policies.
For some cmdlets, you must provide the credentials of the storage account in use.
A storage account credential is an access object created in OneSDK that points to an existing Azure storage account.
You provide the name and access key of an existing storage account to create a storage account credential.
You can then use that credential object with other cmdlets.

This cmdlet uses the registration key that you provide when you select the resource by using the **Select-AzureStorSimpleResource** cmdlet.
Be sure that value is correct to avoid encryption failure.
To modify the registration key to a correct value, use **Select-AzureStorSimpleResource**.

## EXAMPLES

### Example 1: Create a credential
```
PS C:\>New-AzureStorSimpleStorageAccountCredential -StorageAccountName "ContosoAccount07" -StorageAccountKey "L/eVcHtvqKjPWm5SaAJXtDlc0d69yVs0ICoZ2XIV1x0r9TqUyQyLUNS8lHvTvRmzdvQhJelav3fYyX7wyAu/SA==" -UseSSL $False -WaitForComplete
VERBOSE: ClientRequestId: f363cda4-54aa-4ee8-a3fa-00651ac86ffb_PS
VERBOSE: Found storage account with name : ContosoAccount07
VERBOSE: Storage credential verification succeeded. 
VERBOSE: ClientRequestId: 716ce6df-62b3-4d48-8e0e-b0c94eec6934_PS
VERBOSE: Encryption in progress... 
VERBOSE: ClientRequestId: 19aa4ef7-2789-4817-980c-19e33d257650_PS

JobId        : 84f74c25-b742-452c-973c-43c7446e9f49
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {}

VERBOSE: The job created for your create operation has completed successfully. 
VERBOSE: ClientRequestId: 72bcdf37-bf06-4dac-adc9-31bb8d06475a_PS
CloudType                        : Azure
Hostname                         : blob.core.windows.net
InstanceId                       : b9986714-cef4-4c3f-a719-7acfc9559320
IsDefault                        : False
Location                         : West Europe
Login                            : ContosoAccount07
Name                             : ContosoAccount07
OperationInProgress              : None

Password                         : G1sBQ6/qAN1gyRGRZVarpi7o6ToJl61sGugfeJ75yx7cwyaGLQHjrSEEwhxThbDJkxso2emAOarTe920Uufy
                                   0AmJ9NpBI5hNyIFfwS4Ff+z2WmfKOzApyeofW5Zy7GPufehe/2ondq0XG4pGt3qxHFXNVUuiaPSU6TVWEKSh
                                   hWDaksSXYMGij3DJdZDW1MA49e6Q7OY+rFujbYvi9P2OjVj8T+FbiMtMB5NnQEqE+t3k74RqPIDKU+d3h9x4
                                   rYbAksGPfMvSa0fUipwYJ+Y5/NABA6j/MfB2pNDJbvqDoa1JCX6SKiwL81wmTh78/KnDY5ST3Said5DzKEbR
                                   iYMQZg==
PasswordEncryptionCertThumbprint : 
UseSSL                           : False
VolumeCount                      : 0
```

This command creates a storage access credential for the specified storage account.
This command specifies the *WaitForComplete* parameter, and, so, the cmdlet waits until the task finishes to return control to the console.

### Example 2: Create a credential and query that status of the task
```
PS C:\>New-AzureStorSimpleStorageAccountCredential -Name "ContosoAccount08" -Key "6BlMpSVrCQVQy3iOpkxiyY8uk/e3PiHIhadxV4qpPlKInr/eRFrGcWKDrfNC1IHj6oh0If/h3rALdZ0zuaf9cQ==" -UseSSL $True
PS C:\> Get-AzureStorSimpleTask -InstanceId "53816d8d-a8b5-4c1d-a177-e59007608d6d"
VERBOSE: ClientRequestId: 6104a834-ea57-4687-8e0b-1d97dc1c038b_PS
VERBOSE: Found storage account with name : ContosoAccount08
VERBOSE: Storage credential verification succeeded. 
VERBOSE: ClientRequestId: 1f686fa4-5afc-43c3-87b6-f2da7bf9e65f_PS
VERBOSE: Encryption in progress... 
VERBOSE: ClientRequestId: 8acb3770-bd72-43e6-9622-481002ad40b0_PS
53816d8d-a8b5-4c1d-a177-e59007608d6d
VERBOSE: The create task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
53816d8d-a8b5-4c1d-a177-e59007608d6d for tracking the task's status
```

The first command creates a storage access credential for the specified storage account.
The command returns a task ID.

The second command queries the status of the task by using the **Get-AzureStorSimpleTask** cmdlet.
The command specifies the task ID from the first command.

### Example 3: Create a credential to use with another cmdlet
```
PS C:\>Get-AzureStorSimpleStorageAccountCredential -Name "ContosoAccount09" | New-AzureStorSimpleDeviceVolumeContainer -Name "VC03" -DeviceName "Contoso63-AppVm" -BandWidthRate 256 -EncryptionEnabled $True -EncryptionKey "<your encryption key>" -WaitForComplete
VERBOSE: ClientRequestId: b1d1e637-cd72-4a1e-95a8-4db1d0b921a7_PS
VERBOSE: ClientRequestId: 71f56ca0-1f0b-4655-9331-4849e096345a_PS
VERBOSE: ClientRequestId: fbdd5a96-c95f-4547-9bcd-376d05543348_PS
VERBOSE: Storage Access Credential with name ContosoAccount09 found! 
VERBOSE: ClientRequestId: b44e0363-9979-4e97-aeb1-d9eb4073a337_PS
VERBOSE: ClientRequestId: a6047943-b01e-44e4-a91d-5103aa80ce57_PS
VERBOSE: Encryption in progress... 
VERBOSE: ClientRequestId: ac2dfd8b-922f-4e4d-8c8d-df1e2f87806c_PS


JobId        : 1cf2db5d-624f-46c4-97b9-c36451ba144e
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The job created for your create operation has completed successfully. 
VERBOSE: ClientRequestId: 9558414b-0883-4cf6-8a02-40efc7edd80d_PS
BandwidthRate                   : 256
EncryptionKey                   : g53NTgCF3SBVZzzk+9yUz5nZopvZpNr3th92ol7WRO7ZUKhodPm7WNjjHEKB0/V+JY6P68tdaF4JxF5jH58e/
                                  mCtTvnPNpOxykYFdY9GKGd9gnf+36sUPqiLFP+ONO5nN/N/zFmOeyuySsaa3gJsZG8eIiFc821yfe9m5QPbF
                                  bx/Qyu8qLl1R1LrKU7k+46IXfwQYSyclztydyuzvFUUic9kaJuR3944VLvrjvxJIbnLrYy7hsn+Gfq7ds9NFq
                                  AUILBH0+bk2uWgUlofAcE8fJ/rzDAHr8nFGWxOTJSrqAo0J3st8BN39+BcrY+zOWsMc/vKfc+Ss5PsGVGDT1r
                                  eQ==
InstanceId                      : 60c34706-ef0c-4c6f-ad90-7249f42648f7
IsDefault                       : False
IsEncryptionEnabled             : True
Name                            : VC03
OperationInProgress             : None
Owned                           : True
PrimaryStorageAccountCredential : Microsoft.WindowsAzure.Management.StorSimple.Models.StorageAccountCredentialResponse
SecretsEncryptionThumbprint     : 
VolumeCount                     : 0
```

This command creates a storage account credential.
The command then passes that credential to the **New-AzureStorSimpleDeviceVolumeContainer** cmdlet by using the pipeline operator.
That cmdlet creates a new volume container by using the credential.

## PARAMETERS

### -Endpoint
Specifies the Azure storage endpoint for the storage account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

### -StorageAccountKey
Specifies the access key of the storage account in plain text.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Key

Required: True
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

Required: True
Position: 3
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
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### IEnumerable<StorageAccountCredentialResponse>, TaskResponse
This cmdlet returns a list of **StorageAccountCredentialResponse** objects, if you specify the *WaitForComplete* parameter.
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

[Remove-AzureStorSimpleStorageAccountCredential](.\Remove-AzureStorSimpleStorageAccountCredential.md)

[Set-AzureStorSimpleStorageAccountCredential](.\Set-AzureStorSimpleStorageAccountCredential.md)

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

[New-AzureStorSimpleDeviceVolumeContainer](.\New-AzureStorSimpleDeviceVolumeContainer.md)

