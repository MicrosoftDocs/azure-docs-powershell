### Example 1: Get usage data aggregated by day
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "2019-12-30T00:00:00Z" -ReportedEndTime "2019-12-31T00:00:00Z" -AggregationGranularity Daily
```

Get the usage data for the entire day of 30th Dec 2019 (in UTC) for all tenants under provider aggregated by the day. ReportedStartTime and ReportedEndTime must be rounded to days. If called as the service administrator, this effectively shows all usage data for every tenant. 

### Example 2: Get usage data aggregated by the hour
```powershell
Get-AzsSubscriberUsage -ReportedStartTime "2019-12-30T00:00:00Z" -ReportedEndTime "2019-12-30T02:00:00Z" -AggregationGranularity Hourly
```

Get the usage data between  12am - 2am on 30th Dec 2019 (in UTC) aggregated by the hour. ReportedStartTime and ReportedEndTime must be rounded to hours. Likewise, if called as the service administrator, this effectively shows all usage data for every tenant.

