---
external help file: Az.ComputeSchedule-help.xml
Module Name: Az.ComputeSchedule
online version: https://learn.microsoft.com/powershell/module/az.computeschedule/get-azcomputescheduleoperationstatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ComputeSchedule/ComputeSchedule/help/Get-AzComputeScheduleOperationStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ComputeSchedule/ComputeSchedule/help/Get-AzComputeScheduleOperationStatus.md
cmdletStatusMessage: This cmdlet is part of a **Preview** module. Preview versions aren't recommended for use in production environments. For more information, see https://aka.ms/azps-refstatus.
cmdletStatus: preview
---
# Get-AzComputeScheduleOperationStatus

## SYNOPSIS
VirtualMachinesGetOperationStatus: Polling endpoint to read status of operations performed on virtual machines

## SYNTAX

```
Get-AzComputeScheduleOperationStatus -Location <String> [-SubscriptionId <String[]>] -CorrelationId <String>
 -OperationId <String[]> [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
VirtualMachinesGetOperationStatus: Polling endpoint to read status of operations performed on virtual machines

## EXAMPLES

### Example 1: Poll the status of operations performed on a batch of virtual machines using the operation id from a previous Start/Deallocate/Hibernate operation
```powershell
Get-AzComputeScheduleOperationStatus -Location "eastus2euap" -Correlationid "aaaa0000-bb11-2222-33cc-444444dddddd" -OperationId "bbbb1111-cc22-3333-44dd-555555eeeeee","cccc2222-dd33-4444-55ee-666666ffffff" -SubscriptionId "aaaa0a0a-bb1b-cc2c-dd3d-eeeeee4e4e4e" | Format-List
```

```output
ErrorCode                      :
ErrorDetail                    :
OperationCompletedAt           : 12/18/2024 5:09:20 AM
OperationDeadline              : 12/18/2024 5:08:36 AM
OperationDeadlineType          : InitiateAt
OperationId                    : bbbb1111-cc22-3333-44dd-555555eeeeee
OperationOpType                : Start
OperationResourceId            : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/test-resource-group/providers/Microsoft.Compute/virtualMachines/exesta83600
OperationState                 : Succeeded
OperationSubscriptionId        : a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1
OperationTimezone              :
ResourceId                     : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/test-resource-group/providers/Microsoft.Compute/virtualMachines/exesta83600
ResourceOperationErrorCode     :
ResourceOperationErrorDetail   :
RetryPolicyRetryCount          : 3
RetryPolicyRetryWindowInMinute : 30

ErrorCode                      :
ErrorDetail                    :
OperationCompletedAt           : 12/18/2024 5:04:18 AM
OperationDeadline              : 12/18/2024 5:03:15 AM
OperationDeadlineType          : InitiateAt
OperationId                    : cccc2222-dd33-4444-55ee-666666ffffff
OperationOpType                : Hibernate
OperationResourceId            : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/test-resource-group/providers/Microsoft.Compute/virtualMachines/exeHib80440
OperationState                 : Succeeded
OperationSubscriptionId        : a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1
OperationTimezone              :
ResourceId                     : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/test-resource-group/providers/Microsoft.Compute/virtualMachines/exeHib80440
ResourceOperationErrorCode     :
ResourceOperationErrorDetail   :
RetryPolicyRetryCount          : 3
RetryPolicyRetryWindowInMinute : 30
```

The above command cancels scheduled operations (Start/Deallocate/Hibernate) on virtual machines using the operationids gotten from previous Execute/Submit type API calls

## PARAMETERS

### -CorrelationId
CorrelationId item

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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

### -Location
The location name.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationId
The list of operation ids to get the status of

```yaml
Type: System.String[]
Parameter Sets: (All)
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
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeSchedule.Models.IGetOperationStatusResponse

## NOTES

## RELATED LINKS
