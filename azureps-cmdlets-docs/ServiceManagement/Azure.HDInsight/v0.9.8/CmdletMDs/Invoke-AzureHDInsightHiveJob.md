---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# Invoke-AzureHDInsightHiveJob

## SYNOPSIS
Submits Hive queries to an HDInsight cluster, shows progress of the query execution, and gets query results in one operation.

## SYNTAX

```
Invoke-AzureHDInsightHiveJob [-Arguments <String[]>] [-Defines <Hashtable>] [-File <String>]
 [-Files <String[]>] [-JobName <String>] [[-Query] <String>] [-RunAsFileJob] [-StatusFolder <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **Invoke-AzureHDInsightHiveJob** cmdlet submits Hive queries to an HDInsight cluster, displays the progress of the query execution, and gets the query results in one operation.
You must run the Use-AzureHDInsightCluster cmdlet before running **Invoke-AzureHDInsightHiveJob** to specify the HDInsight cluster to which to submit a query.

## EXAMPLES

### 1: Submit a Hive query
```
PS C:\>Use-AzureHDInsightCluster "Cluster01" -Subscription (Get-AzureSubscription -Current).SubscriptionId 
PS C:\> Invoke-AzureHDInsightHiveJob "select * from hivesampletable limit 10"
```

The first command uses the **Use-AzureHDInsightCluster** cmdlet to specify a cluster in the current subscription to use for a Hive query.

The second command uses the **Invoke-AzureHDInsightHiveJob** cmdlet to submit the Hive query.

## PARAMETERS

### -Arguments
Specifies an array of arguments for a Hadoop job.
The arguments are passed as command-line arguments to each task.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Defines
Specifies Hadoop configuration values to set when a job runs.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: Params

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -File
Specifies the Windows Azure Storage Blob (WASB) path to a file in Azure blob storage that contains the query to run.
You can use this parameter instead of the *Query* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: QueryFile

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Files
Specifies a collection of files that are required for a Hive job.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Specifies the name of a Hive job.
If you do not specify this parameter, this cmdlet uses the default value: "Hive: \<first 100 characters of Query\>".

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query
Specifies a Hive query.

```yaml
Type: String
Parameter Sets: (All)
Aliases: QueryText

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusFolder
Specifies the location of the folder that contains standard outputs and error outputs for a job, including its exit code and task logs.

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

### -Profile
Specifies an Azure profile.
If you do not specify this parameter, this cmdlet uses the local default profile.

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

### -RunAsFileJob
Indicates that this cmdlet creates a file in the default Azure storage account in which to store a query.
This cmdlet submits the job that references this file as a script to run.

You can use this functionality to handle special characters such as percent sign (%) that would fail on a job submission through Templeton, because Templeton interprets a query with a percent sign as a URL parameter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureHDInsightHiveJobDefinition](.\New-AzureHDInsightHiveJobDefinition.md)

[Use-AzureHDInsightCluster](.\Use-AzureHDInsightCluster.md)

