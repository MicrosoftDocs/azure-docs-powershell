---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Set-AzureVMSqlServerExtension.md
schema: 2.0.0
---

# New-AzureVMSqlServerAutoPatchingConfig

## SYNOPSIS
Creates a configuration object for virtual machine automatic patching.

## SYNTAX

```
New-AzureVMSqlServerAutoPatchingConfig [-Enable] [-DayOfWeek <String>] [-MaintenanceWindowStartingHour <Int32>]
 [-MaintenanceWindowDuration <Int32>] [-PatchCategory <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVMSqlServerAutoPatchingConfig** cmdlet creates a configuration object for virtual machine automatic patching.

## EXAMPLES

### Example 1: Create a configuration object to configure automatic patching
```
PS C:\>$APS = New-AzureVMSqlServerAutoPatchingConfig -Enable -DayOfWeek "Thursday" -MaintenanceWindowStartingHour 11 -MaintenanceWindowDuration 120 -PatchCategory "Important"
          Enable                        : True
          DayOfWeek                     : Thursday
          MaintenanceWindowStartingHour : 11
          MaintenanceWindowDuration     : 120
          PatchCategory                 : Important
```

This command creates configuration object that can be used to configure automatic patching using Set-AzureVMSqlServerExtension.

## PARAMETERS

### -Enable
Indicates that automated patching for the virtual machine is enabled.
If you enable automated patching the cmdlet will put Windows Update into interactive mode.
If you disable automated patching, Windows Update settings will not change.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DayOfWeek
Specifies the day of the week when updates should be installed.

The acceptable values for this parameter are:

- Sunday
- Monday
- Tuesday
- Wednesday
- Thursday
- Friday
- Saturday
- Everyday

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaintenanceWindowStartingHour
Specifies the hour of the day when maintenance window starts.
This time defines when updates start installing and is rounded to the hour.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaintenanceWindowDuration
Specifies the duration of the maintenance window.
Automated patching will avoid performing an action that can impact a virtual machine availability outside of that window.
Only 30 minutes increments are allowed.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PatchCategory
Specifies whether important updates should be included.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
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
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

### AutoPatchingSettings
This cmdlet returns object contains settings for automated patching.

## NOTES

## RELATED LINKS

[Set-AzureVMSqlServerExtension](.\Set-AzureVMSqlServerExtension.md)

[Remove-AzureVMSqlServerExtension](.\Remove-AzureVMSqlServerExtension.md)

[Set-AzureVMSqlServerExtension](.\Set-AzureVMSqlServerExtension.md)

