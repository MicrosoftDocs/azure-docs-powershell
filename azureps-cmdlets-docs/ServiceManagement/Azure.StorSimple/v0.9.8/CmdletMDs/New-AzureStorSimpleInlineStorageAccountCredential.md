---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleStorageAccountCredential.md
schema: 2.0.0
---

# New-AzureStorSimpleInlineStorageAccountCredential

## SYNOPSIS
Creates an inline storage account credential.

## SYNTAX

```
New-AzureStorSimpleInlineStorageAccountCredential [-StorageAccountName] <String> [-StorageAccountKey] <String>
 [[-Endpoint] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorSimpleInlineStorageAccountCredential** cmdlet creates an inline Azure storage account credential object.
This cmdlet creates a dummy credential object.
You can use the **New-AzureStorSimpleDeviceVolumeContainer** cmdlet and the current cmdlet in the same command by using the Windows PowerShell pipeline.
The actual storage account credential object is created as part of creation of the volume container.

## EXAMPLES

### Example 1: Create a storage account credential inline
```
PS C:\>New-AzureStorSimpleInlineStorageAccountCredential -Name "contoso76" -Key x6o/tpZh8Coo8Tteo0NHLksTOKr/P9Vufo0LZNGdPGVTSUu00/p6ta1w9gRbVBNjzN8aa504kH2zkEsfUme+kw== | New-AzureStorSimpleDeviceVolumeContainer -Name "VolumeContainer_06" -DeviceName Contoso_App3 -BandWidthRate 256 -EncryptionEnabled $True -EncryptionKey "Key22" -WaitForComplete
VERBOSE: ClientRequestId: 535d24d5-1ed8-4759-92b2-dd492f94e23e_PS
VERBOSE: ClientRequestId: f32fc069-96c9-4fd9-a71a-0e62d81f25d8_PS
VERBOSE: ClientRequestId: 4376a931-89f5-448f-92bd-b2f7234244c9_PS
VERBOSE: ClientRequestId: 980109d4-7d76-40d0-ae3c-db539e2cb486_PS
VERBOSE: Encryption in progress... 
VERBOSE: Creating StorageAccountCredential inline
VERBOSE: Found storage account with name : contoso76
VERBOSE: Storage credential verification succeeded. 
VERBOSE: Encryption in progress... 
VERBOSE: ClientRequestId: d4f8a5de-bf81-4773-b6e6-edb034284cf4_PS


JobId        : 2dec64d3-b30d-4d35-adb3-12689b235b79
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep, 
               Microsoft.WindowsAzure.Management.StorSimple.Models.TaskStep}

VERBOSE: The job created for your create operation has completed successfully. 
VERBOSE: ClientRequestId: abd4082a-2eda-42ad-8cb3-5864dd2f7d1f_PS
BandwidthRate                   : 256
EncryptionKey                   : SK23I39L7GvoLce7u63TMT/A/V/TW8JXe+PoXKEKzwsr3t/h7tdqV1EpfaK0DGO/qo5b2PLCagFHAxnZEiejg
                                  jtF9TcyK+aLyzEnkqtM+eNRJmgANzJ9C/5L6Ubp+eSWiy+U/pyZygxPrb37e0yFg+qbHV9R9Qi+afBpHD9Gsi
                                  rhURuOc/idWG29eaEifuRzn/zEjvwJ2pEyYLcsuL+ftfRYZom69XO+cRDv5yT3xdNI/dAod/5YUaf1IhJl8wR
                                  cWjqyr00NxlCI03hTgH2sFyTFZWc07S2KI5K5n3rmCL6vGT76SRgNFeUxGz3v06/VoBhdmv9vDfrEz5UkW04d
                                  Qw==
InstanceId                      : a72bf4bb-0f0a-4ec2-a8b1-c4548825f522
IsDefault                       : False
IsEncryptionEnabled             : True
Name                            : VolumneContainer_06
OperationInProgress             : None
Owned                           : True
PrimaryStorageAccountCredential : Microsoft.WindowsAzure.Management.StorSimple.Models.StorageAccountCredentialResponse
SecretsEncryptionThumbprint     : 
VolumeCount                     : 0
```

This command creates a storage account credential inline, and then passes it to the **New-AzureStorSimpleDeviceVolumeContainer** cmdlet by using the pipeline operator.
That container uses the dummy credential to create a volume container.

## PARAMETERS

### -Endpoint
Specifies the Azure storage endpoint for the storage account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
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

### -StorageAccountKey
Specifies the account key of the storage account in plain text.
The key is transferred in encrypted format.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### StorageAccountCredentialResponse
This cmdlet returns a **CloudType** object, which contains the following fields: 

- **Hostname**.
**String**. 
- **InstanceId**.
**String**. 
- **IsDefault**.
**Boolean**. 
- **Location**.
**String**. 
- **Login**.
**String**. 
- **Name**.
**String**. 
- **OperationInProgress**.
**OperationInProgress**. 
- **Password**.
**String**. 
- **PasswordEncryptionCertThumbprint**.
**String**. 
- **UseSSL**.
**Boolean**. 
- **VolumeCount**.
**Integer**.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleStorageAccountCredential](.\New-AzureStorSimpleStorageAccountCredential.md)

[New-AzureStorSimpleDeviceVolumeContainer](.\New-AzureStorSimpleDeviceVolumeContainer.md)

