---
external help file:
Module Name: Azs.Subscriptions.Admin
online version: https://docs.microsoft.com/powershell/module/azs.subscriptions.admin/get-azsmanifest
schema: 2.0.0
---

# Get-AzsManifest

## SYNOPSIS
Get the specified manifest.

## SYNTAX

### List (Default)
```
Get-AzsManifest [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Get
```
Get-AzsManifest -ManifestName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzsManifest -INPUTOBJECT \<ISubscriptionsAdminIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Get the specified manifest.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-AzsManifest

Name     : Microsoft-Authorization-Admin--redmond--Admin
Metadata : Microsoft.Azure.PowerShell.Cmdlets.SubscriptionsAdmin.Models.Api20151101.ManifestMetadata

Name     : Microsoft-Authorization--redmond--Admin
Metadata : Microsoft.Azure.PowerShell.Cmdlets.SubscriptionsAdmin.Models.Api20151101.ManifestMetadata
```

Lists all the manifests under the current subscription.

## PARAMETERS

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

### -InputObject
Identity Parameter
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.SubscriptionsAdmin.Models.ISubscriptionsAdminIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False

```

### -ManifestName
The manifest name.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -SubscriptionId
Subscription credentials which uniquely identify Microsoft Azure subscription.The subscription ID forms part of the URI for every service call.

```yaml
Type: System.String[]
Parameter Sets: Get, List
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

### Microsoft.Azure.PowerShell.Cmdlets.SubscriptionsAdmin.Models.ISubscriptionsAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.SubscriptionsAdmin.Models.Api20151101.IManifest

ALIASES

## NOTES

COMPLEX PARAMETER PROPERTIES
To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.

INPUTOBJECT \<ISubscriptionsAdminIdentity>: Identity Parameter
  - `[DelegatedProvider <String>]`: DelegatedProvider identifier.
  - `[DelegatedProviderSubscriptionId <String>]`: Delegated provider subscription identifier.
  - `[Id <String>]`: Resource identity path
  - `[Location <String>]`: The AzureStack location.
  - `[ManifestName <String>]`: The manifest name.
  - `[Offer <String>]`: Name of an offer.
  - `[OfferDelegationName <String>]`: Name of a offer delegation.
  - `[OperationsStatusName <String>]`: The operation status name.
  - `[Plan <String>]`: Name of the plan.
  - `[PlanAcquisitionId <String>]`: The plan acquisition Identifier
  - `[Quota <String>]`: Name of the quota.
  - `[ResourceGroupName <String>]`: The resource group the resource is located under.
  - `[SubscriptionId <String>]`: Subscription credentials which uniquely identify Microsoft Azure subscription.The subscription ID forms part of the URI for every service call.
  - `[TargetSubscriptionId <String>]`: The target subscription ID.
  - `[Tenant <String>]`: Directory tenant name.

## RELATED LINKS
