---
external help file:
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/get-azsdisk
schema: 2.0.0
---

# Get-AzsDisk

## SYNOPSIS
Returns the disk.

## SYNTAX

### List (Default)
```
Get-AzsDisk [-Location <String>] [-SubscriptionId <String[]>] [-Count <Int32>] [-ScaleUnit <String>]
 [-SharePath <String>] [-Start <Int32>] [-Status <String>] [-UserSubscriptionId <String>]
 [-VolumeLabel <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Get
```
Get-AzsDisk -Name <String> [-Location <String>] [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzsDisk -InputObject <IComputeAdminIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Returns the disk.

## EXAMPLES

### Example 1: Get All Disks 
```powershell
PS C:\> Get-AzsDisk
```

Without any parameters, `Get-AzsDisk` will list all Disks.

### Example 2: Get a Disk by Name
```powershell
PS C:\> Get-AzsDisk -Name "426b8945-8a24-42ad-acdc-c26f16202489"

ActualSizeGb    : 24
DiskId          : 426b8945-8a24-42ad-acdc-c26f16202489
DiskSku         : Premium_LRS
DiskType        : Disk
Id              : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/north
                  west/disks/426b8945-8a24-42ad-acdc-c26f16202489
Location        : northwest
ManagedBy       :
Name            : northwest/426b8945-8a24-42ad-acdc-c26f16202489
ProvisionSizeGb : 127
SharePath       : \\SU1FileServer.azs-long02-int.selfhost.corp.microsoft.com\SU1_ObjStore_3
Status          : Unattached
Type            : Microsoft.Compute.Admin/locations/disks
UserResourceId  : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/resourceGroups/LADTEST/providers/Microsoft.Comput
                  e/Disks/TEST_OsDisk_1_426b89458a2442adacdcc26f16202489
```

Specify a disk by its `Name` to retrieve it.

### Example 3: Get a Specified number of Disks
```powershell
PS C:\>  Get-AzsDisk -Count 3

ActualSizeGb    : 24
DiskId          : 20f1619e-4210-47f6-81e6-b89e3028df06
DiskSku         : Premium_LRS
DiskType        : Disk
Id              : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/north
                  west/disks/20f1619e-4210-47f6-81e6-b89e3028df06
Location        : northwest
ManagedBy       :
Name            : northwest/20f1619e-4210-47f6-81e6-b89e3028df06
ProvisionSizeGb : 127
SharePath       : \\SU1FileServer.azs-long02-int.selfhost.corp.microsoft.com\SU1_ObjStore_4
Status          : Unattached
Type            : Microsoft.Compute.Admin/locations/disks
UserResourceId  : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/resourceGroups/RG1/providers/Microsoft.Compute/Di
                  sks/TEST_OsDisk_1_20f1619e421047f681e6b89e3028df06

ActualSizeGb    : 24
DiskId          : 38a767e4-4ceb-49fb-a53c-48de9b08aaae
DiskSku         : Standard_LRS
DiskType        : Disk
Id              : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/north
                  west/disks/38a767e4-4ceb-49fb-a53c-48de9b08aaae
Location        : northwest
ManagedBy       :
Name            : northwest/38a767e4-4ceb-49fb-a53c-48de9b08aaae
ProvisionSizeGb : 127
SharePath       : \\SU1FileServer.azs-long02-int.selfhost.corp.microsoft.com\SU1_ObjStore_4
Status          : Unattached
Type            : Microsoft.Compute.Admin/locations/disks
UserResourceId  : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/resourceGroups/SCTE/providers/Microsoft.Compute/D
                  isks/SCTETest_OsDisk_1_38a767e44ceb49fba53c48de9b08aaae

ActualSizeGb    : 24
DiskId          : 426b8945-8a24-42ad-acdc-c26f16202489
DiskSku         : Premium_LRS
DiskType        : Disk
Id              : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/north
                  west/disks/426b8945-8a24-42ad-acdc-c26f16202489
Location        : northwest
ManagedBy       :
Name            : northwest/426b8945-8a24-42ad-acdc-c26f16202489
ProvisionSizeGb : 127
SharePath       : \\SU1FileServer.azs-long02-int.selfhost.corp.microsoft.com\SU1_ObjStore_3
Status          : Unattached
Type            : Microsoft.Compute.Admin/locations/disks
UserResourceId  : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/resourceGroups/LADTEST/providers/Microsoft.Comput
                  e/Disks/TEST_OsDisk_1_426b89458a2442adacdcc26f16202489
```

Use the `Count` parameter to retrieve a specific number of disks.

### Example 4: Get all disks in specific location
```powershell
PS C:\> Get-AzsDisk -Status All -ScaleUnit s-cluster -VolumeLabel Objstore_4

ActualSizeGb    : 2
DiskId          : e4732f76-0753-40ec-80f5-8effdd0b437d
DiskSku         : Premium_LRS
DiskType        : Disk
Id              : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/providers/Microsoft.Compute.Admin/locations/redmond/disks/e4732f76-0753-40ec-80f5-8effdd0b437d
Location        : redmond
ManagedBy       : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/rbactest/providers/Microsoft.Compute/virtualMachines/test1
Name            : redmond/e4732f76-0753-40ec-80f5-8effdd0b437d
ProvisionSizeGb : 30
SharePath       : \\SU1FileServer.s11r0401.masd.stbtest.microsoft.com\SU1_ObjStore_4
Status          : Reserved
Type            : Microsoft.Compute.Admin/locations/disks
UserResourceId  : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/RBACTEST/providers/Microsoft.Compute/Disks/test1_OsDisk_1_e4732f76075340ec80f58effdd0b437d

ActualSizeGb    : 1
DiskId          : 0485cbc9-1efa-43bd-86c2-0e201d79c528
DiskSku         : Premium_LRS
DiskType        : Disk
Id              : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/providers/Microsoft.Compute.Admin/locations/redmond/disks/0485cbc9-1efa-43bd-86c2-0e201d79c528
Location        : redmond
ManagedBy       : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/rbactest/providers/Microsoft.Compute/virtualMachines/test1
Name            : redmond/0485cbc9-1efa-43bd-86c2-0e201d79c528
ProvisionSizeGb : 64
SharePath       : \\SU1FileServer.s11r0401.masd.stbtest.microsoft.com\SU1_ObjStore_4
Status          : Reserved
Type            : Microsoft.Compute.Admin/locations/disks
UserResourceId  : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/TESTRG1/providers/Microsoft.Compute/Disks/gpsdisk

ActualSizeGb    : 1
DiskId          : 137893db-e7ce-4907-a488-b35c5e928614
DiskSku         : Premium_LRS
DiskType        : Disk
Id              : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/providers/Microsoft.Compute.Admin/locations/redmond/disks/137893db-e7ce-4907-a488-b35c5e928614
Location        : redmond
ManagedBy       : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/rbactest/providers/Microsoft.Compute/virtualMachines/test1
Name            : redmond/137893db-e7ce-4907-a488-b35c5e928614
ProvisionSizeGb : 55
SharePath       : \\SU1FileServer.s11r0401.masd.stbtest.microsoft.com\SU1_ObjStore_4
Status          : Reserved
Type            : Microsoft.Compute.Admin/locations/disks
UserResourceId  : /subscriptions/7829c784-cd3f-464a-b195-3be83c964c9c/resourceGroups/RBACTEST/providers/Microsoft.Compute/Disks/testdd
```

Use the `ScaleUnit` or `VolumeLabel` parameter to list all disks in specific location

## PARAMETERS

### -Count
The maximum number of disks to return.

```yaml
Type: System.Int32
Parameter Sets: List
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
The disk guid as identity.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DiskId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -ScaleUnit
The scale unit which the resource belongs to.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -SharePath
The share which the resource belongs to.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -Start
The start index of disks in query.

```yaml
Type: System.Int32
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -Status
The parameters of disk state.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
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

### -UserSubscriptionId
User Subscription Id which the resource belongs to.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### -VolumeLabel
The volume label of the volume which the resource belongs to.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False

```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.IComputeAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api20180730Preview.IDisk



## NOTES

COMPLEX PARAMETER PROPERTIES
To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.

INPUTOBJECT <IComputeAdminIdentity>: Identity Parameter
  - `[DiskId <String>]`: The disk guid as identity.
  - `[Id <String>]`: Resource identity path
  - `[Location <String>]`: Location of the resource.
  - `[MigrationId <String>]`: The migration job guid name.
  - `[Offer <String>]`: Name of the offer.
  - `[Publisher <String>]`: Name of the publisher.
  - `[QuotaName <String>]`: Name of the quota.
  - `[Sku <String>]`: Name of the SKU.
  - `[SubscriptionId <String>]`: Subscription credentials that uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
  - `[Type <String>]`: Type of extension.
  - `[Version <String>]`: The version of the resource.

## RELATED LINKS

