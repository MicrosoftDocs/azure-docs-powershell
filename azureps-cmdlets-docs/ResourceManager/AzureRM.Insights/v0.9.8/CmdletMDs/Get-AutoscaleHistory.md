---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Add-AutoscaleSetting.md
schema: 2.0.0
---

# Get-AutoscaleHistory

## SYNOPSIS
Retrieves Autoscale events.

## SYNTAX

```
Get-AutoscaleHistory [-ResourceId <String>] [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>]
 [-Caller <String>] [-DetailedOutput] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AutoscaleHistory** cmdlet retrieves events related to an Autoscale setting.

## EXAMPLES

### Example 1: Retrieve all Autoscale events
```
PS C:\>Get-AutoscaleHistory -StartTime 2015-02-09T18:35:00 -EndTime 2015-02-09T18:40:00 -DetailedOutput
```

This command retrieves all the Autoscale-related events associated to the current subscription

### Example 2: Retrieve Autoscale history for a particular resource
```
PS C:\>Get-AutoscaleHistory -StartTime 2015-02-09T18:35:00 -EndTime 2015-02-09T18:40:00 -ResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.insights/autoscalesettings/DefaultServerFarm-Default-Web-EastUS" -DetailedOutput
Authorization        : 
Caller               : Microsoft.Insights/autoscaleSettings
Claims               : 
                       http://schemas.xmlsoap.org/ws/2005/05/identity/claims/spn: Microsoft.Insights/autoscaleSettings
CorrelationId        : ac5b03ca-05d4-4811-9c27-0314a145f785
Description          : The autoscale engine attempting to scale resource '/subscriptions/a93fb07c-6c93-40be-bf3b-4f0deb
                       a10f4b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm'
                       from 1 instances count to 2 instances count. 
EventChannels        : Admin, Operation

. . . 


Status               : Succeeded
SubmissionTimestamp  : 2/10/2015 2:38:19 AM
SubscriptionId       : b93fb07a-6f93-30be-bf3e-4f0deca15f4f
SubStatus            :
```

This command retrieves the Autoscale-related events associated to the resource that has the specified resource ID.

## PARAMETERS

### -ResourceId
Specifies the resource ID of the resource associated with the Autoscale setting for which this cmdlet gets history.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies the start time, as a **DateTime** object, of the history information that this cmdlet gets.
Specify a value in local time.
The default value is one hour before the current local time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Specifies the end time, as a **DateTime** object, of the history information that this cmdlet gets.
Specify a value in local time.
For more information about **DateTime**, type `Get-Help Get-Date`.The default value is the current time.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Specifies a status for which this cmdlet gets Autoscale history.
The default value is all statuses.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Caller
Specifies a caller for which this cmdlet gets Autoscale history.
The default value is all callers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DetailedOutput
Indicates that this cmdlet displays detailed information about the objects that it retrieves.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AutoscaleSetting](.\Add-AutoscaleSetting.md)

[Get-AutoscaleSetting](.\Get-AutoscaleSetting.md)

[Remove-AutoscaleSetting](.\Remove-AutoscaleSetting.md)

