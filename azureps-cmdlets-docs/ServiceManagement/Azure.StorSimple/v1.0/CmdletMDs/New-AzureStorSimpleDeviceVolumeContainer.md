---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceVolumeContainer.md
schema: 2.0.0
---

# New-AzureStorSimpleDeviceVolumeContainer

## SYNOPSIS
Creates a volume container.

## SYNTAX

```
New-AzureStorSimpleDeviceVolumeContainer [-DeviceName] <String> [-VolumeContainerName] <String>
 [-PrimaryStorageAccountCredential] <StorageAccountCredentialResponse> [-BandWidthRateInMbps] <Int32>
 [[-EncryptionEnabled] <Boolean>] [[-EncryptionKey] <String>] [-WaitForComplete] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorSimpleDeviceVolumeContainer** cmdlet creates a volume container.
You must associate a storage account credential with the new volume container.
To obtain a storage account credential, use the **Get-AzureStorSimpleStorageAccountCredential** cmdlet.

## EXAMPLES

### Example 1: Create a container
```
PS C:\>Get-AzureStorSimpleStorageAccountCredential -StorageAccountName "ContosoAccount" | New-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "Container08" -BandWidthRateInMbps 256
VERBOSE: ClientRequestId: 96a4ccd4-f2a9-4820-8bc8-e6b7b56dce0d_PS
VERBOSE: ClientRequestId: 90be20db-098a-4f2b-a6da-9da6f533a846_PS
VERBOSE: ClientRequestId: 410fd33a-8fa3-4ae5-a1bf-1b6da9b34ffc_PS
VERBOSE: Storage Access Credential with name ContosoAccount found! 
VERBOSE: ClientRequestId: 0a6d1008-ba1f-43b2-a424-9c86be2fb83b_PS
VERBOSE: ClientRequestId: 08f0d657-a130-4a25-8090-270c58b479dc_PS
VERBOSE: ClientRequestId: 0f3e894a-b031-467c-a258-41b74c89cf18_PS
5b192120-9df0-40ed-b75e-b4e728bd37ef
VERBOSE: The create task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
5b192120-9df0-40ed-b75e-b4e728bd37ef for tracking the task's status
```

This command gets the storage account credential for the account named ContosoAccount by using the **Get-AzureStorSimpleStorageAccountCredential** cmdlet.
The command passes the credential to the current cmdlet by using the pipeline operator.
This cmdlet uses the credential from that cmdlet to create the container named Container08 on the device named Contoso63-AppVm.
This command starts the job, and then returns a **TaskResponse** object.
To see the status of the job, use the **Get-AzureStorSimpleTask** cmdlet.

## PARAMETERS

### -BandWidthRateInMbps
Specifies the bandwidth rate in megabits per second (Mbps).

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: CloudBandwidthInMbps

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device on which to create the volume container.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionEnabled
Indicates whether to enable encryption.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKey
Specifies the encryption key.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryStorageAccountCredential
Specifies the credential, as a **StorageAccountCredential** object, to associate with the new volume container.
To obtain a **StorageAccountCredential** object, use the **Get-AzureStorSimpleStorageAccountCredential** cmdlet.

```yaml
Type: StorageAccountCredentialResponse
Parameter Sets: (All)
Aliases: StorageAccount

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
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

### -VolumeContainerName
Specifies the name of the volume container to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
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
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### StorageAccountCredential
This cmdlet accepts a **PrimaryStorageAccountCredential** object to associate with the volume container.

## OUTPUTS

### TaskStatusInfo
This cmdlet returns a **TaskStatusInfo** object, if you specify the *WaitForComplete* parameter.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceVolumeContainer](.\Get-AzureStorSimpleDeviceVolumeContainer.md)

[Remove-AzureStorSimpleDeviceVolumeContainer](.\Remove-AzureStorSimpleDeviceVolumeContainer.md)

[Get-AzureStorSimpleStorageAccountCredential](.\Get-AzureStorSimpleStorageAccountCredential.md)

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

