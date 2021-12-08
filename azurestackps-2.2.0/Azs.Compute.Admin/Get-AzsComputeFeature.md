---
external help file:
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/get-azscomputefeature
schema: 2.0.0
---

# Get-AzsComputeFeature

## SYNOPSIS
Get an existing feature.

## SYNTAX

### List (Default)
```
Get-AzsComputeFeature [-Location <String>] [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Get
```
Get-AzsComputeFeature -Name <String> [-Location <String>] [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzsComputeFeature -INPUTOBJECT \<IComputeAdminIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Get an existing feature.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```powershell
Get-AzsComputeFeature -Location local -Name Microsoft.Compute.EmergencyVMAccess | ConvertTo-Json
```

{
    "EnabledTenantSubscriptionId":  [
                                        "e9f233f4-6251-441e-a8e4-5e0165a5ff84",
                                        "a6293671-ca91-4040-8edc-5a5bc8bb10f2",
                                        "77df6e8d-c86b-4184-a7da-35217afdb7e8",
                                        "078fcd45-e064-4f1b-a546-f2873757c7c0",
                                        "88e0ade6-f94a-4a75-8b32-b8f07daf2ad0",
                                        "22c12f96-7352-4165-a7e4-ccebd1257f15",
                                        "a40a4cdf-0054-4b41-8692-0c0de49958b5",
                                        "d23289dc-887a-4e68-8c84-8a0e4d8dec51",
                                        "3f843028-3d49-4ae9-8185-148745b4a231"
                                    ],
    "FeatureName":  "Microsoft.Compute.EmergencyVMAccess",
    "GlobalFeatureSettingGlobalFeatureState":  {

                                               },
    "Id":  "/subscriptions/52cc3943-24b0-45bc-8403-466ccf5775a3/providers/Microsoft.Compute.Admin/locations/local/features/Microsoft.Compute.EmergencyVMAccess",
    "Location":  "local",
    "Name":  "Microsoft.Compute.EmergencyVMAccess",
    "Type":  "Microsoft.Compute.Admin/locations/features"
}

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
Location of the resource.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Name of the feature.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: FeatureName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Subscription credentials that uniquely identify Microsoft Azure subscription.
The subscription ID forms part of the URI for every service call.

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

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api20201101.IFeature

## NOTES

ALIASES

COMPLEX PARAMETER PROPERTIES

To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.


INPUTOBJECT \<IComputeAdminIdentity>: Identity Parameter
  - `[DiskId <String>]`: The disk guid as identity.
  - `[FeatureName <String>]`: Name of the feature.
  - `[Id <String>]`: Resource identity path
  - `[Location <String>]`: Location of the resource.
  - `[MigrationId <String>]`: The migration job guid name.
  - `[Offer <String>]`: Name of the offer.
  - `[Publisher <String>]`: Name of the publisher.
  - `[QuotaName <String>]`: Name of the quota.
  - `[ScaleUnitName <String>]`: Name of the scale unit.
  - `[Sku <String>]`: Name of the SKU.
  - `[SubscriptionId <String>]`: Subscription credentials that uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
  - `[Type <String>]`: Type of extension.
  - `[Version <String>]`: The version of the resource.

## RELATED LINKS

