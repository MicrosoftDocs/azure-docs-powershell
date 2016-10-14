---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Get-AutoscaleSetting.md
schema: 2.0.0
---

# Add-AutoscaleSetting

## SYNOPSIS
Creates an Autoscale setting.

## SYNTAX

### Parameters for AddAustoscaleSetting cmdlet in the update semantics
```
Add-AutoscaleSetting -SettingSpec <AutoscaleSettingResource> -ResourceGroup <String> [-DisableSetting]
 [-AutoscaleProfiles <System.Collections.Generic.List`1[Microsoft.Azure.Management.Insights.Models.AutoscaleProfile]>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### Parameters for AddAustoscaleSetting cmdlet in the create semantics
```
Add-AutoscaleSetting -Location <String> -Name <String> -ResourceGroup <String> [-DisableSetting]
 [-AutoscaleProfiles <System.Collections.Generic.List`1[Microsoft.Azure.Management.Insights.Models.AutoscaleProfile]>]
 -TargetResourceId <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AutoscaleSetting** cmdlet creates an Autoscale setting.

## EXAMPLES

### Example 1: Create Autoscale setting
```
PS C:\>$Rule01 = New-AutoscaleRule -MetricName Requests -MetricResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosowebsite" -Operator GreaterThan -MetricStatistic Average -Threshold 10 -TimeGrain 00:01:00 -ScaleActionCooldown 00:05:00 -ScaleActionDirection Increase -ScaleActionScaleType ChangeCount -ScaleActionValue "1" 
PS C:\> $Rule02 = New-AutoscaleRule -MetricName Requests -MetricResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.web/sites/contosowebsite" -Operator GreaterThan -MetricStatistic Average -Threshold 10 -TimeGrain 00:01:00 -ScaleActionCooldown 00:10:00 -ScaleActionDirection Increase -ScaleActionScaleType ChangeCount -ScaleActionValue "2"
PS C:\> $Profile01 = New-AutoscaleProfile -DefaultCapacity "1" -MaximumCapacity "10" -MinimumCapacity "1" -StartTimeWindow 2015-03-05T14:00:00 -EndTimeWindow 2015-03-05T14:30:00 -TimeWindowTimeZone GMT -Rules $Rule01, $Rule02 -Name "ContosoProfile"
PS C:\> $Profile02 = New-AutoscaleProfile -DefaultCapacity "1" -MaximumCapacity "10" -MinimumCapacity "1" -Rules $Rule01, $Rule02 -Name "secondProfileName" -RecurrenceFrequency Minute -ScheduleDays "1", "2", "3" -ScheduleHours 5, 10, 15 -ScheduleMinutes 15, 30, 45 -ScheduleTimeZone "GMT"
PS C:\> Add-AutoscaleSetting -Location "East US" -Name "ContosoSetting07" -ResourceGroup "Default-Web-EastUS" -TargetResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm" -AutoscaleProfiles $Profile01, $Profile02
```

The first two commands create Autoscale rules, and then store them in the $Rule01 and $Rule02 variables.

The next two commands create Autoscale profiles that use the rules stored in $Rule01 and $Rule02, and then store the profiles in the $Profile01 and $Profile02 variables.

The final command adds an Autoscale setting that includes the profiles stored in $Profile01 and $Profile02.

## PARAMETERS

### -SettingSpec
Specifies an Autoscale setting.
To obtain an **AutoscaleSettingResource** object, use the Get-AutoscaleSetting cmdlet.

```yaml
Type: AutoscaleSettingResource
Parameter Sets: Parameters for AddAustoscaleSetting cmdlet in the update semantics
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Specifies the name of the resource group of the resource that is associated to the Autoscale setting.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableSetting
Indicates that this cmdlet disables an existing Autoscale setting.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoscaleProfiles
Specifies an array of profiles that this cmdlet adds to the Autoscale setting.
To add a setting without any profiles, do not specify this parameter.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Management.Insights.Models.AutoscaleProfile]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Location
Specifies a location for the Autoscale setting.

```yaml
Type: String
Parameter Sets: Parameters for AddAustoscaleSetting cmdlet in the create semantics
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the Autoscale setting.

```yaml
Type: String
Parameter Sets: Parameters for AddAustoscaleSetting cmdlet in the create semantics
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetResourceId
Specifies the ID of the resource to autoscale.

```yaml
Type: String
Parameter Sets: Parameters for AddAustoscaleSetting cmdlet in the create semantics
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AutoscaleSetting](.\Get-AutoscaleSetting.md)

[Remove-AutoscaleSetting](.\Remove-AutoscaleSetting.md)

[Get-AutoscaleHistory](.\Get-AutoscaleHistory.md)

