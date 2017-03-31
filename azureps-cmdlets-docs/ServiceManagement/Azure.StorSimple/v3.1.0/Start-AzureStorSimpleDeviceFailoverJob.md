---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: 53580FF1-D905-40FD-A5F0-D5FBCD036E0B
online version: 
schema: 2.0.0
---

# Start-AzureStorSimpleDeviceFailoverJob

## SYNOPSIS
Initiates a failover operation of volume container groups.

## SYNTAX

### Empty (Default)
```
Start-AzureStorSimpleDeviceFailoverJob
 [-VolumecontainerGroups] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainerGroup]>
 [-Force] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### IdentifyById
```
Start-AzureStorSimpleDeviceFailoverJob [-DeviceId] <String>
 [-VolumecontainerGroups] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainerGroup]>
 [-TargetDeviceId] <String> [-Force] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### IdentifyByName
```
Start-AzureStorSimpleDeviceFailoverJob [-DeviceName] <String>
 [-VolumecontainerGroups] <System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainerGroup]>
 [-TargetDeviceName] <String> [-Force] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureStorSimpleDeviceFailoverJob** cmdlet initiates a failover operation of one or more volume container groups from one device to another.

## EXAMPLES

### Example 1: Start a failover job for a named device and named target device
```
PS C:\>(Get-AzureStorSimpleFailoverVolumeContainers -DeviceName "ChewD_App7") | Where-Object {$_.IsDCGroupEligibleForDR -eq $True} | Start-AzureStorSimpleDeviceFailoverJob -DeviceName "ChewD_App7" -TargetDeviceName "Fuller05" -Force
a3d902be-8ffb-42a4-bbf8-0a1b30db71b2_0ee59ae9-0293-46e2-ae56-bc308c8e5520
```

This command gets the failover volume containers for the device named ChewD_App7 by using the **Get-AzureStorSimpleFailoverVolumeContainers** cmdlet.
The command passes the results to the **Where-Object** cmdlet, which drops those containers that have a value other than $True for the **IsDCGroupEligibleForDR** property.
For more information, type `Get-Help Where-Object`.
The current cmdlet starts failover jobs for the remaining failover volume containers.
The command specifies the device name and target device name.
The command returns the instance ID of the job that the cmdlet starts.

### Example 2: Start a failover job for a device and target device specified by ID
```
PS C:\>(Get-AzureStorSimpleFailoverVolumeContainers -DeviceId "3825f272-1efb-4c14-b63f-22605ce3b925") | Where-Object {$_.IsDCGroupEligibleForDR -eq $True} | Select-Object -First 1 | Start-AzureStorSimpleDeviceFailoverJob -DeviceId "3825f272-1efb-4c14-b63f-22605ce3b925" -TargetDeviceId "0ee59ae9-0293-46e2-ae56-bc308c8e5520" -Force
4c5ac0d0-4b66-465c-98f5-aec90505ad12_0ee59ae9-0293-46e2-ae56-bc308c8e5520
```

This command gets the failover volume containers for the device named ChewD_App7 by using **Get-AzureStorSimpleFailoverVolumeContainers**.
The command passes the results to **Where-Object**, which drops those containters that have a value other than $True for the **IsDCGroupEligibleForDR** property.
The cmdlet passes the results to the **Select-Object** cmdlet, which selects the first object to pass to the current cmdlet.
For more information, type `Get-Help Select-Object`.
The current cmdlet starts failover jobs for the selected failover volume container.
The command specifies the device ID and target device ID.
The command returns the instance ID of the job that the cmdlet starts.

## PARAMETERS

### -VolumecontainerGroups
Specifies the list of volume container groups that this cmdlet fails over to another device.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.WindowsAzure.Management.StorSimple.Models.DataContainerGroup]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceId
Specifies the instance ID of the StorSimple device on which the volume container groups exist.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDeviceId
Specifies the instance ID of the StorSimple device to which this cmdlet fails over the volume container groups.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device on which the volume container groups exist.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDeviceName
Specifies the name of the StorSimple device to which this cmdlet fails over the volume container groups.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### List\<DataContainerGroup\>
You can pipe a list of volume container groups to this cmdlet.

## OUTPUTS

### String

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleFailoverVolumeContainers](./Get-AzureStorSimpleFailoverVolumeContainers.md)


