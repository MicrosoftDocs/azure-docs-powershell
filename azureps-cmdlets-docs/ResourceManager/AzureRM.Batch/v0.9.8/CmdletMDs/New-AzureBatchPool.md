---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccountKeys.md
schema: 2.0.0
---

# New-AzureBatchPool

## SYNOPSIS
Creates a new pool in the Batch service under the specified account.

## SYNTAX

### TargetDedicated (Default)
```
New-AzureBatchPool [-Id] <String> -VirtualMachineSize <String> -OSFamily <String> [-DisplayName <String>]
 [-TargetOSVersion <String>] [-ResizeTimeout <TimeSpan>] [-TargetDedicated <Int32>]
 [-MaxTasksPerComputeNode <Int32>] [-TaskSchedulingPolicy <PSTaskSchedulingPolicy>] [-Metadata <IDictionary>]
 [-InterComputeNodeCommunicationEnabled] [-StartTask <PSStartTask>]
 [-CertificateReferences <PSCertificateReference[]>] -BatchContext <BatchAccountContext>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### AutoScale
```
New-AzureBatchPool [-Id] <String> -VirtualMachineSize <String> -OSFamily <String> [-DisplayName <String>]
 [-TargetOSVersion <String>] [-AutoScaleFormula <String>] [-MaxTasksPerComputeNode <Int32>]
 [-TaskSchedulingPolicy <PSTaskSchedulingPolicy>] [-Metadata <IDictionary>]
 [-InterComputeNodeCommunicationEnabled] [-StartTask <PSStartTask>]
 [-CertificateReferences <PSCertificateReference[]>] -BatchContext <BatchAccountContext>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureBatchPool** cmdlet creates a new pool in the Azure Batch service under the account specified by the *BatchContext* parameter.

## EXAMPLES

### Example 1: Create a new pool using the TargetDedicated parameter set
```
PS C:\>New-AzureBatchPool -Id "MyPool" -VirtualMachineSize "small" -OSFamily "4" -TargetOSVersion "*" -TargetDedicated 3 -BatchContext $Context
```

This command creates a new pool with id MyPool using the TargetDedicated parameter set.
The target allocation is three compute nodes.
The pool will use small virtual machines imaged with the latest operating system version of family four.

### Example 2: Create a new pool using the AutoScale parameter set
```
PS C:\>New-AzureBatchPool -Id "AutoScalePool" -VirtualMachineSize "small" -OSFamily "4" -TargetOSVersion "*" -AutoScaleFormula '$TargetDedicated=2;' -BatchContext $Context
```

This command creates a new pool with ID AutoScalePool using the AutoScale parameter set.
The pool will use small virtual machines imaged with the latest operating system version of family four, and the target number of compute nodes will be determined by the Autoscale formula.

## PARAMETERS

### -AutoScaleFormula
Specifies the formula for automatically scaling the pool.
For more information on Autoscale formulas, see Define the Autoscaling Formula for a Poolhttps://msdn.microsoft.com/en-us/library/azure/dn820182.aspx (https://msdn.microsoft.com/en-us/library/azure/dn820182.aspx) in the Microsoft Developer Network Library.

```yaml
Type: String
Parameter Sets: AutoScale
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BatchContext
Specifies the **BatchAccountContext** instance that this cmdlet uses to interact with the Batch service.
To obtain a **BatchAccountContext** object that contains access keys for your subscription, use the Get-AzureBatchAccountKeys cmdlet.

```yaml
Type: BatchAccountContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificateReferences
Specifies certificates associated with the pool.
The Batch service installs the referenced certificates on each compute node of the pool.

```yaml
Type: PSCertificateReference[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the pool to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InterComputeNodeCommunicationEnabled
Indicates that this cmdlet sets up the pool for direct communication between dedicated compute nodes.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTasksPerComputeNode
Specifies the maximum number of tasks that can run on a single compute node.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metadata
Specifies the metadata, as key/value pairs, to add to the new pool.
The key is the metadata name.
The value is the metadata value.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSFamily
Specifies the operating system family of the compute nodes in the pool.
For more information about operating system families and versions, see Azure Guest OS Releases and SDK Compatibility Matrixhttp://azure.microsoft.com/en-us/documentation/articles/cloud-services-guestos-update-matrix/ (http://azure.microsoft.com/en-us/documentation/articles/cloud-services-guestos-update-matrix/) in the Microsoft Developer Library.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResizeTimeout
Specifies the timeout for allocating compute nodes to the pool.

```yaml
Type: TimeSpan
Parameter Sets: TargetDedicated
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTask
Specifies the start task specification for the pool.
The start task is run when a compute node joins the pool, or when the compute node is rebooted or reimaged.

```yaml
Type: PSStartTask
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDedicated
Specifies the target number of compute nodes to allocate to the pool.

```yaml
Type: Int32
Parameter Sets: TargetDedicated
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetOSVersion
Specifies the target operating system version of the compute nodes in the pool.
You can use "*" for the latest operating system version for the specified family.
For more information about operating system families and versions, see Azure Guest OS Releases and SDK Compatibility Matrixhttp://azure.microsoft.com/en-us/documentation/articles/cloud-services-guestos-update-matrix/ (http://azure.microsoft.com/en-us/documentation/articles/cloud-services-guestos-update-matrix/) in the Microsoft Developer Network Library.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskSchedulingPolicy
Specifies the task scheduling policy, such as the ComputeNodeFillType.

```yaml
Type: PSTaskSchedulingPolicy
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineSize
Specifies the size of the virtual machines in the pool.
For more information on virtual machine sizes, see Sizes for Virtual Machineshttps://azure.microsoft.com/en-us/documentation/articles/virtual-machines-size-specs/ (https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-size-specs/) in the Microsoft Developer Network Library.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureBatchAccountKeys](.\Get-AzureBatchAccountKeys.md)

[Get-AzureBatchPool](.\Get-AzureBatchPool.md)

[Remove-AzureBatchPool](.\Remove-AzureBatchPool.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

