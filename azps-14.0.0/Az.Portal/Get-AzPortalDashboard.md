---
external help file: Az.Portal-help.xml
Module Name: Az.Portal
online version: https://learn.microsoft.com/powershell/module/az.portal/get-azportaldashboard
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Portal/Portal/help/Get-AzPortalDashboard.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Portal/Portal/help/Get-AzPortalDashboard.md
---

# Get-AzPortalDashboard

## SYNOPSIS
Gets the Dashboard.

## SYNTAX

### List (Default)
```
Get-AzPortalDashboard [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Get
```
Get-AzPortalDashboard -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### List1
```
Get-AzPortalDashboard -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzPortalDashboard -InputObject <IPortalIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets the Dashboard.

## EXAMPLES

### Example 1: List all dashboards in a subscription
```powershell
Get-AzPortalDashboard
```

```output
Location Name                                           Type
-------- ----                                           ----
eastasia my-custom-dashboard1                           Microsoft.Portal/dashboards
westus   my-second-custom-dashboard1                    Microsoft.Portal/dashboards
```

List all dashboards in a subscription

### Example 2: Get details for a single Portal Dashboard
```powershell
Get-AzPortalDashboard -ResourceGroupName my-rg -Name mydashboard
```

```output
Location Name        Type
-------- ----        ----
eastus   mydashboard Microsoft.Portal/dashboards
```

Get details for a single dashboard

## PARAMETERS

### -DefaultProfile
The DefaultProfile parameter is not functional.
Use the SubscriptionId parameter when available if executing the cmdlet against a different subscription.

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

### -InputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Portal.Models.IPortalIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
The name of the dashboard.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DashboardName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the resource group.
The name is case insensitive.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The ID of the target subscription.
The value must be an UUID.

```yaml
Type: System.String[]
Parameter Sets: List, Get, List1
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

### Microsoft.Azure.PowerShell.Cmdlets.Portal.Models.IPortalIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Portal.Models.IDashboard

## NOTES

## RELATED LINKS
