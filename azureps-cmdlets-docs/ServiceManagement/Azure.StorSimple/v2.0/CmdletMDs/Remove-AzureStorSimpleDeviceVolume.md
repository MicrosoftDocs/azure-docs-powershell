---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleDeviceVolume.md
schema: 2.0.0
---

# Remove-AzureStorSimpleDeviceVolume

## SYNOPSIS
Removes a volume from a StorSimple device.

## SYNTAX

### IdentifyByName
```
Remove-AzureStorSimpleDeviceVolume [-DeviceName] <String> [-VolumeName] <String> [-WaitForComplete] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Remove-AzureStorSimpleDeviceVolume [-DeviceName] <String> [-Volume] <VirtualDisk> [-WaitForComplete] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureStorSimpleDeviceVolume** cmdlet removes a volume from a StorSimple device.
This cmdlet prompts you for confirmation unless you specify the *Force* parameter.

## EXAMPLES

### Example 1: Remove a volume by using the pipeline
```
PS C:\>Get-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume18" | Remove-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm"
VERBOSE: ClientRequestId: 2933e24d-9564-42b5-9053-5f0bc4f59ea8_PS
VERBOSE: ClientRequestId: 7c2d854b-537a-4253-bb0c-c15bc8aa2b49_PS
VERBOSE: ClientRequestId: 4bf749ac-517c-49e7-8027-a8f62e272014_PS
VERBOSE: ClientRequestId: 7d9ec87a-616d-4ca9-bfb8-158859174d59_PS

Confirm
Are you sure you want to remove the volume? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
VERBOSE: ClientRequestId: 67a38e28-a015-44b1-8159-c1a6604f4d81_PS
VERBOSE: About to run a job to remove your volume! 
VERBOSE: ClientRequestId: 56101c10-07ca-40f4-8f19-c6fdd895e3a5_PS
32925451-4451-4478-89f7-d8930505d3fb
VERBOSE: The delete task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
32925451-4451-4478-89f7-d8930505d3fb for tracking the task's status
VERBOSE: Volume with name: Volume18 is found.
```

This command gets the volume named Volume18 on the device named Contoso63-AppVm, and then passes that volume to the current cmdlet by using the pipeline operator.
The current cmdlet starts the task that removes the volume, and then returns a **TaskResponse** object.
To see the status of the task, use the **Get-AzureStorSimpleTask** cmdlet.
The command does not specify the *Force* parameter, so the cmdlet prompts you for confirmation.

### Example 2: Remove a volume without confirmation
```
PS C:\>Remove-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "Volume18" -Force
VERBOSE: ClientRequestId: 72f13290-41eb-4ac4-9535-da1a42d0fa0b_PS
VERBOSE: ClientRequestId: ae0c1d99-1a66-4a69-9260-f2c8c12546bd_PS
VERBOSE: ClientRequestId: 9610744f-d031-488f-87e6-3ecddb305e13_PS
VERBOSE: About to run a job to remove your volume! 
VERBOSE: ClientRequestId: d33525d8-7276-4d2a-942d-d10f8078f1f7_PS
483f8cb4-ebc3-46a9-a9e6-0989e25738a0
VERBOSE: The delete task is submitted successfully. Please use the command Get-AzureStorSimpleTask -InstanceId
483f8cb4-ebc3-46a9-a9e6-0989e25738a0 for tracking the task's status
```

This command removes the volume named Volume18 from the device named Contoso63-AppVm.
The command specifies the *Force* parameter, so the cmdlet does not prompt you for confirmation.

## PARAMETERS

### -DeviceName
Specifies the name of the StorSimple device on which to the volume to remove exists.

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

### -Volume
Specifies the volume to remove, as a **VirtualDisk** object.
To obtain a **VirtualDisk** object, use the **Get-AzureStorSimpleDeviceVolume** cmdlet.

```yaml
Type: VirtualDisk
Parameter Sets: IdentifyByObject
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeName
Specifies the name of the volume to remove.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: Name

Required: True
Position: 2
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
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### VirtualDisk
This cmdlet accepts either the **VirtualDisk** object to delete or the volume name of the **VirtualDisk** to delete.

## OUTPUTS

### TaskStatusInfo
This cmdlet returns a **TaskStatusInfo** object, if you specify the *WaitForComplete* parameter.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleDeviceVolume](.\Get-AzureStorSimpleDeviceVolume.md)

[New-AzureStorSimpleDeviceVolume](.\New-AzureStorSimpleDeviceVolume.md)

[Set-AzureStorSimpleDeviceVolume](.\Set-AzureStorSimpleDeviceVolume.md)

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

