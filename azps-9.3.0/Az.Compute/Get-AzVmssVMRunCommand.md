---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmssvmruncommand
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVmssVMRunCommand.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVmssVMRunCommand.md
---

# Get-AzVmssVMRunCommand

## SYNOPSIS
The operation to get the VMSS VM run command.

## SYNTAX

```
Get-AzVmssVMRunCommand -ResourceGroupName <String> -VMScaleSetName <String> -InstanceId <String>
 [-RunCommandName <String>] [-Expand <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The operation to get the VMSS VM run command.

## EXAMPLES

### Example 1: Get a Run Command for VMSS VM instance

```powershell
Get-AzVmssVMRunCommand  -ResourceGroupName MyRG0 -VMScaleSetName MyVMSS -InstanceId 0 -RunCommandName MyRunCommand
```

Get a Run Command for VM without Instance View.

### Example 2: Get a Run Command for VMSS VM instance with Instance View

```powershell
$x = Get-AzVmssVMRunCommand  -ResourceGroupName MyRG0 -VMScaleSetName MyVMSS -InstanceId 0 -RunCommandName MyRunCommand -Expand InstanceView
$x.InstanceView
```

```output
ExecutionState   : Succeeded
ExecutionMessage :
ExitCode         : 0
Output           :     Directory: C:\


                   Mode                 LastWriteTime         Length Name
                   ----                 -------------         ------ ----
                   -a----        10/27/2022   9:10 PM              0 HelloWorld2022-10-27T21.10.54.9266231+00.00.txt


Error            :
StartTime        : 10/27/2022 9:10:52 PM
EndTime          : 10/27/2022 9:10:55 PM
Statuses         :
```

Get a Run Command for VM with Instance View. Instance View contains execution state of run command (Succeeded, Failed, etc.), exit code, standard output and standard error generated by executing the script using Run Command. A non-zero ExitCode indicates an unsuccessful execution.

### Example 3: Get all Run Commands for a VMSS VM instance

```powershell
Get-AzVmssVMRunCommand -ResourceGroupName MyRG -VMScaleSetName MyVMSS -InstanceId 1
```

Get list of all Run Commands for a VM.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Expand
The expand expression to apply on the operation. For instance view, pass in "InstanceView".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId
Instance ID of the virtual machine for from the VM scale set.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the resource group for the run command.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -RunCommandName
Name of the run command.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMScaleSetName
Name of the virtual machine scale set of the run command.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.Compute.Models.PSVirtualMachineRunCommand

## NOTES

## RELATED LINKS