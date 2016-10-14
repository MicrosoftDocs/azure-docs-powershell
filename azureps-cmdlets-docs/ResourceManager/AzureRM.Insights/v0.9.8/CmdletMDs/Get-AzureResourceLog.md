---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
online version: .\Get-AzureSubscriptionIdLog.md
schema: 2.0.0
---

# Get-AzureResourceLog

## SYNOPSIS
Gets operations for a resource ID.

## SYNTAX

```
Get-AzureResourceLog [-ResourceId] <String> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>]
 [-Caller <String>] [-DetailedOutput] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureResourceLog** cmdlet gets operations associated with a resource ID.

## EXAMPLES

### Example 1: Get operations for the previous hour
```
PS C:\>Get-AzureResourceLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/resourcegroups/Default-Web-CentralUS/providers/Microsoft.Web/serverFarms/Default1"
```

This command displays operations associated to the specified resource ID.
The command displays events that occurred in the default time period, the previous hour.

### Example 2: Get operations after a start time
```
PS C:\>Get-AzureResourceLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/resourcegroups/Default-Web-CentralUS/providers/Microsoft.Web/serverFarms/Default1" -StartTime 2015-01-01T10:30
```

This command displays operations between the start time of 2015-01-01T10:30 and the default end time, which is the current local time.

### Example 3: Get operations between two times
```
PS C:\>Get-AzureResourceLog -ResourceId "/subscriptions/623d50f1-4fa8-4e46-a967-a9214aed43ab/resourcegroups/Default-Web-CentralUS/providers/Microsoft.Web/serverFarms/Default1" -StartTime 2015-01-01T10:30 -EndTime 2015-01-01T11:30
```

This command displays operations that occurred between 2015-01-01T10:30 and 2015-01-01T11:30, local time.

## PARAMETERS

### -ResourceId
Specifies a resource ID for which this cmdlet gets operations.
This parameter is required.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies the start time, as a **DateTime** object, for the operations that this cmdlet gets.
Specify a value in local time.
The default value is one hour before the value of the *EndTime* parameter.

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
Specifies the end time, as a **DateTime** object, for the operations that this cmdlet gets.
Specify a value in local time.
The default value is the current time.
For more information about **DateTime**, type `Get-Help Get-Date`.

Specify a value that is later than the *StartTime* parameter, but not by more than 15 days.

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
Specifies a status for which this cmdlet gets operations.
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
Specifies a caller for which this cmdlet gets operations.
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-AzureSubscriptionIdLog](.\Get-AzureSubscriptionIdLog.md)

[Get-AzureCorrelationIdLog](.\Get-AzureCorrelationIdLog.md)

[Get-AzureResourceGroupLog](.\Get-AzureResourceGroupLog.md)

[Get-AzureResourceProviderLog](.\Get-AzureResourceProviderLog.md)

