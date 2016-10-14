---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Add-AlertRule.md
schema: 2.0.0
---

# Get-AlertHistory

## SYNOPSIS
Retrieves history of alerts.

## SYNTAX

```
Get-AlertHistory [-ResourceId <String>] [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>]
 [-Caller <String>] [-DetailedOutput] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AlertHistory** cmdlet retrieves the history of alerts.
Alerts can have a variety of statuses stored as history.
Statuses include enabled, disabled, raised, and resolved.

## EXAMPLES

### Example 1: Get all alert history
```
PS C:\>Get-AlertHistory -StartTime 2015-02-11T11:00:00 -EndTime 2015-02-11T12:00:00 -DetailedOutput
Authorization        : 
  Caller               : Microsoft.Insights/alertRules
   Claims               : 
                        http://schemas.xmlsoap.org/ws/2005/05/identity/claims/spn: Microsoft.Insights/alertRules
 CorrelationId        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                        microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                        cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                        LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                        LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzg4ODU3OTI5OTI2
 Description          : 'CpuTime GreaterThan 3 ([Count]) in the last 5 minutes' has been resolved for Website: 
                        evannarvaez (Default-Web-EastUS) 
 EventChannels        : Admin, Operation

 . . . 
ResourceProviderName : microsoft.insights
 ResourceId           : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                        microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
 Status               : Activated
 SubmissionTimestamp  : 2/11/2015 7:04:46 PM
 SubscriptionId       : b93fb07a-6f93-30be-bf3e-4f0deca15f4f
 SubStatus            :
```

This command retrieves all the alert rule related events associated to the current subscription.
This command returns details of the objects that it retrieves.
This example displays abridged results.

### Example 2: Get alert history for particular resource
```
PS C:\>Get-AlertHistory -Status 2015-02-11T11:00:00 -EndTime 2015-02-11T12:00:00 -ResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d" -DetailedOutput
Authorization        : 
 Caller               : Microsoft.Insights/alertRules
 Claims               : 
                        http://schemas.xmlsoap.org/ws/2005/05/identity/claims/spn: Microsoft.Insights/alertRules
 CorrelationId        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                        microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                        cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                        LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                        LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzg4ODU3OTI5OTI2
 Description          : 'CpuTime GreaterThan 3 ([Count]) in the last 5 minutes' has been resolved for Website: 
                        evannarvaez (Default-Web-EastUS) 
ResourceGroupName    : Default-Web-EastUS
 ResourceProviderName : microsoft.insights
 ResourceId           : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                        microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
 Status               : Activated
 SubmissionTimestamp  : 2/11/2015 7:04:46 PM
 SubscriptionId       : b93fb07a-6f93-30be-bf3e-4f0deca15f4f
 SubStatus            :
```

This command retrieves the alert rule related events associated to the resource specified by the resource ID.
This command returns details of the objects that it retrieves.
This example displays abridged results.

## PARAMETERS

### -ResourceId
Specifies a resource ID.
This cmdlet gets history for alerts that are associated with the resource that this cmdlet gets.

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
Specifies the start time, as a **DateTime** object, for the alerts for which this cmdlet gets history.
Specify a value in local time.
The default value is one hour before the value of the current local time.

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
Specifies the end time, as a **DateTime** object, for the alerts for which this cmdlet gets history.
For more information about **DateTime**, type `Get-Help Get-Date`.
Specify a value in local time.
The default value is the current time.

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
Specifies a status for which this cmdlet gets alert histories.
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
Specifies a caller for which this cmdlet gets alert history.
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

[Add-AlertRule](.\Add-AlertRule.md)

[Remove-AlertRule](.\Remove-AlertRule.md)

[Get-AlertRule](.\Get-AlertRule.md)

