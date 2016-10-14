---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureHDInsightScriptAction

## SYNOPSIS
Adds an HDInsight script action.

## SYNTAX

```
Add-AzureHDInsightScriptAction [-Config] <AzureHDInsightConfig> [-Name] <String>
 [-ClusterRoleCollection] <ClusterNodeType[]> [-Uri] <Uri> [[-Parameters] <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **Add-AzureHDInsightScriptAction** cmdlet provides Azure HDInsight functionality that is used to install additional software or to change the configuration of applications that run on a Hadoop cluster by using Windows PowerShell ‚Â® scripts.

A script action runs on the cluster nodes when HDInsight clusters are deployed, and they run after nodes in the cluster complete HDInsight configuration.
The script action runs under system administrator account privileges and provides full access rights to the cluster nodes.
You can provide each cluster with a list of script actions to run in a specified sequence.

## EXAMPLES

### Example 1: Add a script action to a cluster
```
PS C:\>$Config = New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4 
PS C:\> $Config = Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction" -Uri http://test.com/test.ps1 -Parameters "test" -ClusterRoleCollection HeadNode,DataNode
PS C:\> New-AzureHDInsightCluster -Config $Config
```

The first command uses the New-AzureHDInsightClusterConfig cmdlet to create an HDInsight cluster configuration, and then stores it in the $Config variable.

The second command uses the **Add-AzureHDInsightScriptAction** cmdlet to add the script action named TestScriptAction to $Config.

The final command uses the New-AzureHDInsightCluster cmdlet to create a new HDInsight cluster that runs the script action stored in $Config.

### Example 2: Add multiple script actions to a cluster
```
PS C:\>$Config = New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4
PS C:\> $Config = Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction1" -Uri http://test.com/test1.ps1 -Parameters "Test1" -ClusterRoleCollection HeadNode,DataNode | Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction2" -Uri http://test.com/test2.ps1 -ClusterRoleCollection HeadNode
PS C:\> New-AzureHDInsightCluster -Config $Config
```

The first command uses the **New-AzureHDInsightClusterConfig** cmdlet to create an HDInsight cluster configuration, and then stores it in the $Config variable.

The second command uses the **Add-AzureHDInsightScriptAction** cmdlet to add the specified script action to $Config, and then uses the pipeline operator to pass $Config to **Add-AzureHDInsightScriptAction** a second time to add a second script action to $Config.

The final command uses the **New-AzureHDInsightCluster** cmdlet to create a cluster that runs the script actions in $Config.

## PARAMETERS

### -ClusterRoleCollection
Specifies the nodes for which to run a script.
The acceptable values for this parameter are: HeadNode or DataNode.

You can specify one value or both values.

```yaml
Type: ClusterNodeType[]
Parameter Sets: (All)
Aliases: 
Accepted values: HeadNode, DataNode, ZookeperNode

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Config
Specifies a configuration object.
This cmdlet adds script action information to the object that this parameter specifies.

```yaml
Type: AzureHDInsightConfig
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a script action.

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

### -Parameters
Specifies the parameters that are required by a script action.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uri
Specifies the URI location of a script to run.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

[New-AzureHDInsightCluster](.\New-AzureHDInsightCluster.md)

[New-AzureHDInsightClusterConfig](.\New-AzureHDInsightClusterConfig.md)

