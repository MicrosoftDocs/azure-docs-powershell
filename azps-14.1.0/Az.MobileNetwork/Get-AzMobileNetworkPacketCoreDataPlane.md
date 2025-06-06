---
external help file: Az.MobileNetwork-help.xml
Module Name: Az.MobileNetwork
online version: https://learn.microsoft.com/powershell/module/az.mobilenetwork/get-azmobilenetworkpacketcoredataplane
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/Get-AzMobileNetworkPacketCoreDataPlane.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/Get-AzMobileNetworkPacketCoreDataPlane.md
---

# Get-AzMobileNetworkPacketCoreDataPlane

## SYNOPSIS
Gets information about the specified packet core data plane.

## SYNTAX

### List (Default)
```
Get-AzMobileNetworkPacketCoreDataPlane -PacketCoreControlPlaneName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentityPacketCoreControlPlane
```
Get-AzMobileNetworkPacketCoreDataPlane -Name <String>
 -PacketCoreControlPlaneInputObject <IMobileNetworkIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Get
```
Get-AzMobileNetworkPacketCoreDataPlane -Name <String> -PacketCoreControlPlaneName <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMobileNetworkPacketCoreDataPlane -InputObject <IMobileNetworkIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets information about the specified packet core data plane.

## EXAMPLES

### Example 1: List information about the specified packet core data plane by PacketCoreControlPlaneName.
```powershell
Get-AzMobileNetworkPacketCoreDataPlane -PacketCoreControlPlaneName azps-mn-pccp -ResourceGroupName azps_test_group
```

```output
Location Name         ResourceGroupName ProvisioningState
-------- ----         ----------------- -----------------
eastus   azps-mn-pcdp azps_test_group   Succeeded
```

List information about the specified packet core data plane by PacketCoreControlPlaneName.

### Example 2: Get information about the specified packet core data plane by Name.
```powershell
Get-AzMobileNetworkPacketCoreDataPlane -PacketCoreControlPlaneName azps-mn-pccp -ResourceGroupName azps_test_group -Name azps-mn-pcdp
```

```output
Location Name         ResourceGroupName ProvisioningState
-------- ----         ----------------- -----------------
eastus   azps-mn-pcdp azps_test_group   Succeeded
```

Get information about the specified packet core data plane by Name.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.IMobileNetworkIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
The name of the packet core data plane.

```yaml
Type: System.String
Parameter Sets: GetViaIdentityPacketCoreControlPlane, Get
Aliases: PacketCoreDataPlaneName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketCoreControlPlaneInputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.IMobileNetworkIdentity
Parameter Sets: GetViaIdentityPacketCoreControlPlane
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PacketCoreControlPlaneName
The name of the packet core control plane.

```yaml
Type: System.String
Parameter Sets: List, Get
Aliases:

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
Parameter Sets: List, Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The ID of the target subscription.

```yaml
Type: System.String[]
Parameter Sets: List, Get
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

### Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.IMobileNetworkIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.IPacketCoreDataPlane

## NOTES

## RELATED LINKS
