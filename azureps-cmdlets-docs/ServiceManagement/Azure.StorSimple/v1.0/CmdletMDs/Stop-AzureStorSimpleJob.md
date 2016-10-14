---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleJob.md
schema: 2.0.0
---

# Stop-AzureStorSimpleJob

## SYNOPSIS
Stops a StorSimple job.

## SYNTAX

```
Stop-AzureStorSimpleJob [-InstanceId] <String> [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-AzureStorSimpleJob** cmdlet stops an on-going StorSimple job.
You can specify a jobs by supplying an instance ID or a job name.

## EXAMPLES

### Example 1: Stop jobs for a device
```
PS C:\>Get-AzureStorSimpleJob -DeviceName "Device07" | Stop-AzureStorSimpleJob -Force
```

This command gets the jobs for the device named Device07, by using the **Get-AzureStorSimpleJob** cmdlet.
The command passes the jobs to the current cmdlet by using the pipeline operator.
The current cmdlet stops any jobs that the command passes to it.
The command specifies the *Force* parameter, and, so, it does not prompt you for confirmation before it stops a job.

### Example 2: Stop a specific job
```
PS C:\>Stop-AzureStorSimpleJob -InstanceId "574f47e0-44e9-495c-b8a5-0203c57ebf6d" -Force
```

This command stops the job that has the specified instance ID.

## PARAMETERS

### -Force
ps_force

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

### -InstanceId
Specifies the ID of the device job to stop.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### DeviceJobDetails
This cmdlet gets details of the **DeviceJob** that this cmdlet stops.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleJob](.\Get-AzureStorSimpleJob.md)

