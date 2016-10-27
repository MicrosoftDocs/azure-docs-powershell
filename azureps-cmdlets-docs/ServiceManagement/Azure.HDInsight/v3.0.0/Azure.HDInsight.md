---
Module Name: Azure.HDInsight
Module Guid: XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
Download Help Link: {{Please enter FwLink manually}}
Help Version: {{Please enter version of help manually (X.X.X.X) format}}
Locale: en-US
---

# Azure.HDInsight Module
## Description
This topic displays help topics for the Azure HDInsight Cmdlets.

>**Note:**This version of Azure PowerShell HDInsight is deprecated. These cmdlets will be removed by January 1, 2017. Please use the newer version of Azure PowerShell HDInsight.
>
For information about how to use the new HDInsight to create a cluster, see [Create Linux-based clusters in HDInsight using Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/). For information about how to submit jobs by using Azure PowerShell and other approaches, see [Submit Hadoop jobs in HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/). For reference information about Azure PowerShell HDInsight, see [Azure HDInsight Cmdlets](https://msdn.microsoft.com/en-us/library/mt438705.aspx).

The Azure PowerShell HDInsight cmdlets manage the Hadoop clusters and the jobs run on them. The HDInsight cmdlets are in the **Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.PSCmdlets** namespace. The cmdlets in the namespace are used to manage the Azure HDInsight Service and Azure blob storage accounts, to create and manage Hadoop clusters, and to submit Hive, Pig, MapReduce, Streaming MapReduce, and Sqoop jobs to these clusters.

## Azure.HDInsight Cmdlets
### [Add-AzureHDInsightConfigValues](./Add-AzureHDInsightConfigValues.md)
Adds a Hadoop configuration value customization or a Hive shared library customization to an HDInsight cluster configuration.


### [Add-AzureHDInsightMetastore](./Add-AzureHDInsightMetastore.md)
Adds a SQL Server database account to an HDInsight cluster configuration.


### [Add-AzureHDInsightScriptAction](./Add-AzureHDInsightScriptAction.md)
Adds an HDInsight script action.


### [Add-AzureHDInsightStorage](./Add-AzureHDInsightStorage.md)
Adds a blob storage account entry to an HDInsight configuration.


### [Get-AzureHDInsightCluster](./Get-AzureHDInsightCluster.md)
Gets an HDInsight cluster.


### [Get-AzureHDInsightJobOutput](./Get-AzureHDInsightJobOutput.md)
Gets the log output for a job.


### [Get-AzureHDInsightJob](./Get-AzureHDInsightJob.md)
Gets HDInsight jobs.


### [Get-AzureHDInsightProperties](./Get-AzureHDInsightProperties.md)
Gets properties specific to an HDInsight service.


### [Grant-AzureHDInsightHttpServicesAccess](./Grant-AzureHDInsightHttpServicesAccess.md)
Grants HTTP access to a cluster.


### [Grant-AzureHdinsightRdpAccess](./Grant-AzureHdinsightRdpAccess.md)
Grants RDP access to an HDInsight cluster.


### [Invoke-AzureHDInsightHiveJob](./Invoke-AzureHDInsightHiveJob.md)
Submits Hive queries to an HDInsight cluster, shows progress of the query execution, and gets query results in one operation.


### [New-AzureHDInsightClusterConfig](./New-AzureHDInsightClusterConfig.md)
Creates a non-persisted HDInsight cluster configuration.


### [New-AzureHDInsightCluster](./New-AzureHDInsightCluster.md)
Creates an HDInsight cluster.


### [New-AzureHDInsightHiveJobDefinition](./New-AzureHDInsightHiveJobDefinition.md)
Defines a new Hive job for an HDInsight service.


### [New-AzureHDInsightMapReduceJobDefinition](./New-AzureHDInsightMapReduceJobDefinition.md)
Defines a new MapReduce job.


### [New-AzureHDInsightPigJobDefinition](./New-AzureHDInsightPigJobDefinition.md)
Defines a new Pig job for an HDInsight service.


### [New-AzureHDInsightSqoopJobDefinition](./New-AzureHDInsightSqoopJobDefinition.md)
Defines a new Sqoop job.


### [New-AzureHDInsightStreamingMapReduceJobDefinition](./New-AzureHDInsightStreamingMapReduceJobDefinition.md)
Defines a new streaming MapReduce job.


### [Remove-AzureHDInsightCluster](./Remove-AzureHDInsightCluster.md)
Deletes an HDInsight cluster from a subscription.


### [Revoke-AzureHDInsightHttpServicesAccess](./Revoke-AzureHDInsightHttpServicesAccess.md)
Disables HTTP access to a cluster.


### [Revoke-AzureHdinsightRdpAccess](./Revoke-AzureHdinsightRdpAccess.md)
Disables RDP access to an HDInsight cluster.


### [Set-AzureHDInsightClusterSize](./Set-AzureHDInsightClusterSize.md)
Sets the number of data nodes for an HDInsight cluster.


### [Set-AzureHDInsightDefaultStorage](./Set-AzureHDInsightDefaultStorage.md)
Sets the default storage account for an HDInsight cluster.


### [Start-AzureHDInsightJob](./Start-AzureHDInsightJob.md)
Starts an HDInsight job.


### [Stop-AzureHDInsightJob](./Stop-AzureHDInsightJob.md)
Stops an HDInsight job.


### [Use-AzureHDInsightCluster](./Use-AzureHDInsightCluster.md)
Selects an HDInsight cluster for the Invoke-AzureHDInsightHiveJob cmdlet to use to submit jobs.


### [Wait-AzureHDInsightJob](./Wait-AzureHDInsightJob.md)
Awaits the completion or failure of an HDInsight job and displays the progress of the job.



