---
external help file: Az.MobileNetwork-help.xml
Module Name: Az.MobileNetwork
online version: https://learn.microsoft.com/powershell/module/az.mobilenetwork/trace-azmobilenetworkcollectpacketcorecontrolplanediagnosticpackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage.md
---

# Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage

## SYNOPSIS
Collect a diagnostics package for the specified packet core control plane.
This action will upload the diagnostics to a storage account.

## SYNTAX

### CollectExpanded (Default)
```
Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage -PacketCoreControlPlaneName <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] -StorageAccountBlobUrl <String>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CollectViaJsonString
```
Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage -PacketCoreControlPlaneName <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] -JsonString <String> [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CollectViaJsonFilePath
```
Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage -PacketCoreControlPlaneName <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] -JsonFilePath <String> [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CollectViaIdentityExpanded
```
Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage -InputObject <IMobileNetworkIdentity>
 -StorageAccountBlobUrl <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Collect a diagnostics package for the specified packet core control plane.
This action will upload the diagnostics to a storage account.

## EXAMPLES

### Example 1: Collect a diagnostics package for the specified packet core control plane.
```powershell
Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage -PacketCoreControlPlaneName azps-mn-pccp -ResourceGroupName azps_test_group -StorageAccountBlobUrl https://azpsstorage.blob.core.windows.net/testdiag/test
```

Collect a diagnostics package for the specified packet core control plane.
This action will upload the diagnostics to a storage account.

## PARAMETERS

### -AsJob
Run the command as a job

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Parameter Sets: CollectViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JsonFilePath
Path of Json file supplied to the Collect operation

```yaml
Type: System.String
Parameter Sets: CollectViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
Json string supplied to the Collect operation

```yaml
Type: System.String
Parameter Sets: CollectViaJsonString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Run the command asynchronously

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PacketCoreControlPlaneName
The name of the packet core control plane.

```yaml
Type: System.String
Parameter Sets: CollectExpanded, CollectViaJsonString, CollectViaJsonFilePath
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
Parameter Sets: CollectExpanded, CollectViaJsonString, CollectViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountBlobUrl
The Storage Account Blob URL to upload the diagnostics package to.

```yaml
Type: System.String
Parameter Sets: CollectExpanded, CollectViaIdentityExpanded
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
Type: System.String
Parameter Sets: CollectExpanded, CollectViaJsonString, CollectViaJsonFilePath
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.IMobileNetworkIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.IAsyncOperationStatus

## NOTES

## RELATED LINKS
