---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Start-AzureStorSimpleDeviceFailoverJob.md
schema: 2.0.0
---

# Get-AzureStorSimpleFailoverVolumeContainers

## SYNOPSIS
Gets the volume container groups for device failover.

## SYNTAX

### IdentifyById
```
Get-AzureStorSimpleFailoverVolumeContainers [-DeviceId] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### IdentifyByName
```
Get-AzureStorSimpleFailoverVolumeContainers [-DeviceName] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleFailoverVolumeContainers** cmdlet gets the volume container groups for device failover.
Pass a single **VolumeContainer** group or an array of **VolumeContainer** groups to the **Start-AzureStorSimpleDeviceFailover** cmdlet.
Only groups that have a value of $True for the **IsDCGroupEligibleForDR** property are eligible for failover.

## EXAMPLES

### Example 1: Get failover volume containers
```
PS C:\>Get-AzureStorSimpleFailoverVolumeContainers -DeviceName "ChewD_App7"

DCGroup                    IneligibilityMessage          IsDCGroupEligibleForDR
-------                    --------------------          ----------------------
{VolumeContainer1889078...                                                 True
{VC_01}                    No cloud snapshot found                        False
{VolumeContainer7306959}   No cloud snapshot found                        False
{VolumeContainer407850151} No cloud snapshot found                        False
```

This command gets failover volume containers.
Only the DCGroups that have a value of $True for the **IsDCGroupEligibleForDR** property can be used for device failover.

## PARAMETERS

### -DeviceId
Specifies the instance ID of the StorSimple device on which to run the cmdlet.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device on which to run the cmdlet.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IList<DataContainerGroup>
This cmdlet returns a list of **VolumeContainer** groups.

## NOTES

## RELATED LINKS

[Start-AzureStorSimpleDeviceFailoverJob](.\Start-AzureStorSimpleDeviceFailoverJob.md)

[Get-AzureStorSimpleDeviceVolumeContainer](.\Get-AzureStorSimpleDeviceVolumeContainer.md)

