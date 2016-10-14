---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureRmBatchAccountKeys.md
schema: 2.0.0
---

# New-AzureBatchPool

## SYNOPSIS
Creates a pool in the Batch service.

## SYNTAX

### TargetDedicated (Default)
```
New-AzureBatchPool [-Id] <String> -VirtualMachineSize <String> [-DisplayName <String>]
 [-ResizeTimeout <TimeSpan>] [-TargetDedicated <Int32>] [-MaxTasksPerComputeNode <Int32>]
 [-TaskSchedulingPolicy <PSTaskSchedulingPolicy>] [-Metadata <IDictionary>]
 [-InterComputeNodeCommunicationEnabled] [-StartTask <PSStartTask>]
 [-CertificateReferences <PSCertificateReference[]>]
 [-ApplicationPackageReferences <PSApplicationPackageReference[]>]
 [-VirtualMachineConfiguration <PSVirtualMachineConfiguration>]
 [-CloudServiceConfiguration <PSCloudServiceConfiguration>] -BatchContext <BatchAccountContext>
 [<CommonParameters>]
```

### AutoScale
```
New-AzureBatchPool [-Id] <String> -VirtualMachineSize <String> [-DisplayName <String>]
 [-AutoScaleEvaluationInterval <TimeSpan>] [-AutoScaleFormula <String>] [-MaxTasksPerComputeNode <Int32>]
 [-TaskSchedulingPolicy <PSTaskSchedulingPolicy>] [-Metadata <IDictionary>]
 [-InterComputeNodeCommunicationEnabled] [-StartTask <PSStartTask>]
 [-CertificateReferences <PSCertificateReference[]>]
 [-ApplicationPackageReferences <PSApplicationPackageReference[]>]
 [-VirtualMachineConfiguration <PSVirtualMachineConfiguration>]
 [-CloudServiceConfiguration <PSCloudServiceConfiguration>] -BatchContext <BatchAccountContext>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureBatchPool** cmdlet creates a pool in the azure_2 Batch service under the account specified by the *BatchContext* parameter.

## EXAMPLES

### Example 1: Create a new pool using the TargetDedicated parameter set
```
PS C:\>New-AzureBatchPool -Id "MyPool" -VirtualMachineSize "Small" -OSFamily "4" -TargetOSVersion "*" -TargetDedicated 3 -BatchContext $Context
```

This command creates a new pool with ID MyPool using the TargetDedicated parameter set.
The target allocation is three compute nodes.
The pool is configured to use small virtual machines imaged with the latest operating system version of family four.

### Example 2: Create a new pool using the AutoScale parameter set
```
PS C:\>New-AzureBatchPool -Id "AutoScalePool" -VirtualMachineSize "Small" -OSFamily "4" -TargetOSVersion "*" -AutoScaleFormula '$TargetDedicated=2;' -BatchContext $Context
```

This command creates a new pool with ID AutoScalePool using the AutoScale parameter set.
The pool is configured to use small virtual machines imaged with the latest operating system version of family four, and the target number of compute nodes are determined by the Autoscale formula.

## PARAMETERS

### -ApplicationPackageReferences
@{Text=}

```yaml
Type: PSApplicationPackageReference[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoScaleEvaluationInterval
Specifies the amount of time, in minutes, that elapses before the pool size is automatically adjusted according to the AutoScale formula.
The default value is 15 minutes, and the minimum value is 5 minutes.

```yaml
Type: TimeSpan
Parameter Sets: AutoScale
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoScaleFormula
Specifies the formula for automatically scaling the pool.

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
To obtain a **BatchAccountContext** object that contains access keys for your subscription, use the Get-AzureRmBatchAccountKeys cmdlet.

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

### -CloudServiceConfiguration
Specifies configuration settings for a pool based on the azure_2 cloud service platform.

```yaml
Type: PSCloudServiceConfiguration
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
Position: 0
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

### -ResizeTimeout
Specifies the time-out for allocating compute nodes to the pool.

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

### -VirtualMachineConfiguration
Specifies configuration settings for a pool on the virtual machines infrastructure.

```yaml
Type: PSVirtualMachineConfiguration
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
For more information about virtual machine sizes, see Sizes for virtual machineshttps://azure.microsoft.com/en-us/documentation/articles/virtual-machines-size-specs/ (https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-size-specs/) in the Microsoft azure_2 site.

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

[Get-AzureRmBatchAccountKeys](.\Get-AzureRmBatchAccountKeys.md)

[Get-AzureBatchPool](.\Get-AzureBatchPool.md)

[Remove-AzureBatchPool](.\Remove-AzureBatchPool.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

