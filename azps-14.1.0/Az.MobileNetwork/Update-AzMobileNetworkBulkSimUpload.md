---
external help file: Az.MobileNetwork-help.xml
Module Name: Az.MobileNetwork
online version: https://learn.microsoft.com/powershell/module/az.mobilenetwork/update-azmobilenetworkbulksimupload
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/Update-AzMobileNetworkBulkSimUpload.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/Update-AzMobileNetworkBulkSimUpload.md
---

# Update-AzMobileNetworkBulkSimUpload

## SYNOPSIS
Bulk upload SIMs to a SIM group.

## SYNTAX

### BulkViaIdentityExpanded (Default)
```
Update-AzMobileNetworkBulkSimUpload -InputObject <IMobileNetworkIdentity> -Sim <ISimNameAndProperties[]>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### BulkViaJsonString
```
Update-AzMobileNetworkBulkSimUpload -ResourceGroupName <String> -SimGroupName <String>
 [-SubscriptionId <String>] -JsonString <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BulkViaJsonFilePath
```
Update-AzMobileNetworkBulkSimUpload -ResourceGroupName <String> -SimGroupName <String>
 [-SubscriptionId <String>] -JsonFilePath <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BulkExpanded
```
Update-AzMobileNetworkBulkSimUpload -ResourceGroupName <String> -SimGroupName <String>
 [-SubscriptionId <String>] -Sim <ISimNameAndProperties[]> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Bulk upload SIMs to a SIM group.

## EXAMPLES

### Example 1: Bulk uploading Sims
```powershell
$sim1 = @{Name = "BulkSim01"; InternationalMobileSubscriberIdentity = "0000000001"; AuthenticationKey = "00000000000000000000000000000001"; OperatorKeyCode = "00000000000000000000000000000001"}
$sim2 = @{Name = "BulkSim02"; InternationalMobileSubscriberIdentity = "0000000002"; AuthenticationKey = "00000000000000000000000000000002"; OperatorKeyCode = "00000000000000000000000000000002"}
$sims = @($sim1,$sim2)
Update-AzMobileNetworkBulkSimUpload -ResourceGroupName azps_test_group -SimGroupName SimGroup01 -Sim $sims
```

Bulks uploads multiple sims into a SimGroup.

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
Parameter Sets: BulkViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JsonFilePath
Path of Json file supplied to the Bulk operation

```yaml
Type: System.String
Parameter Sets: BulkViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
Json string supplied to the Bulk operation

```yaml
Type: System.String
Parameter Sets: BulkViaJsonString
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

### -ResourceGroupName
The name of the resource group.
The name is case insensitive.

```yaml
Type: System.String
Parameter Sets: BulkViaJsonString, BulkViaJsonFilePath, BulkExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sim
A list of SIMs to upload.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MobileNetwork.Models.ISimNameAndProperties[]
Parameter Sets: BulkViaIdentityExpanded, BulkExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SimGroupName
The name of the SIM Group.

```yaml
Type: System.String
Parameter Sets: BulkViaJsonString, BulkViaJsonFilePath, BulkExpanded
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
Parameter Sets: BulkViaJsonString, BulkViaJsonFilePath, BulkExpanded
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
