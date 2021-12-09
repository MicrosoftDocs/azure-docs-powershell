---
external help file:
Module Name: Azs.Commerce.Admin
online version: https://docs.microsoft.com/powershell/module/azs.commerce.admin/get-azssubscriberusage
schema: 2.0.0
---

# Get-AzsSubscriberUsage

## SYNOPSIS
Gets a collection of SubscriberUsageAggregates, which are UsageAggregates from users.

## SYNTAX

```
Get-AzsSubscriberUsage -ReportedEndTime <DateTime> -ReportedStartTime <DateTime> [-SubscriptionId <String[]>]
 [-AggregationGranularity <String>] [-ContinuationToken <String>] [-SubscriberId <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Gets a collection of SubscriberUsageAggregates, which are UsageAggregates from users.

## EXAMPLES

### Example 1: Get usage data aggregated by day
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "2019/12/30" -ReportedEndTime "2019-12-31" -AggregationGranularity Daily
```

Get the usage data for the entire day of 30th Dec 2019 (in UTC) for all tenants under provider aggregated by the day. Specify the date using the format `mm/dd/yyyy`.  
If called as the service administrator, this effectively shows all usage data for every tenant.

### Example 2: Get usage data aggregated by the hour
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "12/30/2019 15:00" -ReportedEndTime "12/30/2019 16:00" -AggregationGranularity Hourly
```

Get the usage data between  3pm - 4am on 30th Dec 2019 (in UTC) aggregated by the hour. Specify the date and time using the format `mm/dd/yyyy HH:MM`.  
Likewise, if called as the service administrator, this effectively shows all usage data for every tenant.

## PARAMETERS

### -AggregationGranularity
The aggregation granularity.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -ContinuationToken
The continuation token.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -ReportedEndTime
The reported end time (exclusive).

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -ReportedStartTime
The reported start time (inclusive).

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -SubscriberId
The tenant subscription identifier.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -SubscriptionId
Subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False

```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Commerce.Models.Api20150601Preview.IUsageAggregate



## NOTES

## RELATED LINKS
