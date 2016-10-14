---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceVolumeContainer.md
schema: 2.0.0
---

# Remove-AzureStorSimpleDeviceVolumeContainer

## SYNOPSIS
Removes a volume container from a StorSimple device.

## SYNTAX

```
Remove-AzureStorSimpleDeviceVolumeContainer [-DeviceName] <String> [-VolumeContainer] <DataContainer>
 [-WaitForComplete] [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureStorSimpleDeviceVolumeContainer** cmdlet removes a volume container object from a StorSimple device.
This cmdlet prompts you for confirmation unless you specify the *Force* parameter.

## EXAMPLES

### Example 1: Remove a container by using the pipeline
```
PS C:\>Get-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -VolumeContainerName "Container08" | Remove-AzureStorSimpleDeviceVolumeContainer -DeviceName "Contoso63-AppVm" -Force
VERBOSE: ClientRequestId: 0efbb4fc-ceb0-4311-bc49-0e08161d0a37_PS
VERBOSE: ClientRequestId: bf5b615f-47e3-4868-91b6-f2d12217a302_PS
VERBOSE: ClientRequestId: 5590c87e-0602-4197-b6c3-cf58b0e7a7b3_PS
VERBOSE: ClientRequestId: b33c71ac-c345-44ff-8213-d7fdf9f8480a_PS
VERBOSE: ClientRequestId: 903d42ef-58f4-4e89-ba7f-5f234262356d_PS
VERBOSE: About to create a job to remove your Volume container! 
VERBOSE: ClientRequestId: 2279575f-5115-4344-9c6f-9ef599bd203e_PS
e9ddec89-67ac-4e2e-a2ed-820de3547bb0
VERBOSE: The delete task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
e9ddec89-67ac-4e2e-a2ed-820de3547bb0 for tracking the task's status
VERBOSE: Volume container with name: Container08 is found.
```

This command gets the volume container named Container08 on the device named Contoso63-AppVm by using the **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet.
The command passes the volume container to the current cmdlet by using the pipeline operator.
This command starts the task to remove the container, and then returns a **TaskResponse** object.
To see the status of the task, use the **Get-AzureStorSimpleTask** cmdlet.
This command specifies the *Force* parameter, so it does not prompt you for confirmation.

## PARAMETERS

### -DeviceName
Specifies the name of the StorSimple device on which to the volume container to remove exists.

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

### -Force
Indicates that this cmdlet does not prompt you for confirmation.

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

### -VolumeContainer
Specifies the volume container to remove, as a **DataContainer** object.
To obtain a **DataContainer** object, use the **Get-AzureStorSimpleDeviceVolumeContainer** cmdlet.

```yaml
Type: DataContainer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WaitForComplete
Indicates that this cmdlet waits for the operation to complete before it returns control to the wps_1 console.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### DataContainer
This cmdlet accepts a **DataContainer** object to remove.

## OUTPUTS

### TaskStatusInfo
This cmdlet returns a **TaskStatusInfo** object, if you specify the *WaitForComplete* parameter.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceVolumeContainer](.\Get-AzureStorSimpleDeviceVolumeContainer.md)

[New-AzureStorSimpleDeviceVolumeContainer](.\New-AzureStorSimpleDeviceVolumeContainer.md)

