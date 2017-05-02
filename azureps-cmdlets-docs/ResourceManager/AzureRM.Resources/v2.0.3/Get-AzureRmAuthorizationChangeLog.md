---
external help file: 
online version: 
schema: 2.0.0
---

# Get-AzureRmAuthorizationChangeLog

## SYNOPSIS
Gets access change history for the selected subscription for the specified time range i.e.
role assignments that were added or removed, including classic administrators (co-administrators and service administrators).
Maximum duration that can be queried is 15 days (going back up to past 90 days).

## SYNTAX

```
Get-AzureRmAuthorizationChangeLog [[-StartTime] <DateTime>] [[-EndTime] <DateTime>] [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureRmAuthorizationChangeLog produces a report of who granted (or revoked) what role to whom at what scope within the subscription for the specified time range. 

The command queries all role assignment events from the Insights resource provider of Azure Resource Manager.
Specifying the time range is optional.
If both StartTime and EndTime parameters are not specified, the default query interval is the past 1 hour.
Maximum duration that can be queried is 15 days (going back up to past 90 days).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-AzureRmAuthorizationChangeLog
```

Gets the access change logs for the past hour.

### -------------------------- EXAMPLE 2 --------------------------
```
Get-AzureRmAuthorizationChangeLog -StartTime "09/20/2015 15:00" -EndTime "09/24/2015 15:00"
```

Gets all access change logs between the specified dates

Timestamp        : 2015-09-23 21:52:41Z
Caller           : admin@rbacCliTest.onmicrosoft.com
Action           : Revoked
PrincipalId      : 54401967-8c4e-474a-9fbb-a42073f1783c
PrincipalName    : testUser
PrincipalType    : User
Scope            : /subscriptions/9004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourceGroups/TestRG/providers/Microsoft.Network/virtualNetworks/testresource
ScopeName        : testresource
ScopeType        : Resource
RoleDefinitionId : /subscriptions/9004a9fd-d58e-48dc-aeb2-4a4aec58606f/providers/Microsoft.Authorization/roleDefinitions/b24988ac-6180-42a0-ab88-20f7382dd24c
RoleName         : Contributor

### -------------------------- EXAMPLE 3 --------------------------
```
Get-AzureRmAuthorizationChangeLog  -StartTime ([DateTime]::Now - [TimeSpan]::FromDays(5)) -EndTime ([DateTime]::Now) | FT Caller, Action, RoleName, PrincipalName, ScopeType
```

Gets access change logs for the past 5 days and format the output

Caller                  Action                  RoleName                PrincipalName           ScopeType
------                  ------                  --------                -------------           ---------
admin@contoso.com       Revoked                 Contributor             User1                   Subscription
admin@contoso.com       Granted                 Reader                  User1                   Resource Group
admin@contoso.com       Revoked                 Contributor             Group1                  Resource

## PARAMETERS

### -EndTime
End time of the query.
Optional

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Start time of the query.
Optional.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

[New-AzureRmRoleAssignment]()

[Get-AzureRmRoleAssignment]()

[Remove-AzureRmRoleAssignment]()

