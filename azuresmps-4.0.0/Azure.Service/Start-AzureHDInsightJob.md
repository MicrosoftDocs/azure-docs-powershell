---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: 60A5ACF7-2637-4BDC-BF41-80E81B23F4CD
online version:
schema: 2.0.0
---

# Start-AzureHDInsightJob

## SYNOPSIS
Starts an HDInsight job.

## SYNTAX

### Start jobDetails on an HDInsight Cluster (Default)
```
Start-AzureHDInsightJob -Cluster <String> [-Credential <PSCredential>]
 -JobDefinition <AzureHDInsightJobDefinition> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
```
Start-AzureHDInsightJob [-Certificate <X509Certificate2>] [-HostedService <String>] -Cluster <String>
 [-Endpoint <Uri>] [-IgnoreSslErrors <Boolean>] -JobDefinition <AzureHDInsightJobDefinition>
 [-Subscription <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see [Create Linux-based clusters in HDInsight using Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/).
For information about how to submit jobs by using Azure PowerShell and other approaches, see [Submit Hadoop jobs in HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/).
For reference information about Azure PowerShell HDInsight, see [Azure HDInsight Cmdlets](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

The **Start-AzureHDInsightJob** cmdlet starts a defined Azure HDInsight job on a specified cluster.
The job to start can be a MapReduce job, a streaming job, a Hive job, or a Pig job.

## EXAMPLES

### Example 1: Start an HDInsight job
```
PS C:\>$SubId = (Get-AzureSubscription -Current).SubscriptionId
PS C:\> $ClusterName = "Cluster01"
PS C:\> $WordCountJob = New-AzureHDInsightMapReduceJobDefinition -JarFile "/Example/Apps/Hadoop-examples.jar" -ClassName "Wordcount" -Defines @{ "mapred.map.tasks" = "3" } -Arguments "/Example/Data/Gutenberg/Davinci.txt", "/Example/Output/WordCount"
PS C:\> $WordCountJob | Start-AzureHDInsightJob -Cluster $ClusterName
    | Wait-AzureHDInsightJob -Subscription $SubId -WaitTimeoutInSeconds 3600
    | Get-AzureHDInsightJobOutput -Cluster $ClusterName -Subscription $SubId -StandardError
```

The first command gets the current subscription ID, and then stores it in the $SubId variable.

The second command assigns the name Cluster01 to the $ClusterName variable.

The third command uses the **New-AzureHDInsightMapReduceJobDefinition** cmdlet to create a MapReduce job definition, and then stores it in the $WordCountJob variable.

The final command uses the pipeline operator to pass the $WordCountJob to the **Start-AzureHDInsightJob** cmdlet to start the job.
After the job starts, it is passed to the **Wait-AzureHDInsightJob** cmdlet, which waits for the job to complete before passing it to the **Get-AzureHDInsightJobOutput** cmdlet to get the job output.

## PARAMETERS

### -Certificate
Specifies the management certificate for an Azure subscription.

```yaml
Type: X509Certificate2
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases: Cert

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cluster
Specifies a cluster.
This cmdlet starts a job on the cluster that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies cluster credentials for direct HTTP access to a cluster.
You can specify this parameter instead of the *Subscription* parameter to authenticate access to a cluster.

```yaml
Type: PSCredential
Parameter Sets: Start jobDetails on an HDInsight Cluster
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Endpoint
Specifies the endpoint to use to connect to Azure.
If you do not specify this parameter, this cmdlet uses the default endpoint.

```yaml
Type: Uri
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostedService
Specifies the namespace of an HDInsight service if you do not want to use the default namespace.

```yaml
Type: String
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases: CloudServiceName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreSslErrors
Indicates whether Secure Sockets Layer (SSL) errors are ignored.

```yaml
Type: Boolean
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobDefinition
Specifies the endpoint to use when connecting to Microsoft Azure if the endpoint is different from the default.

```yaml
Type: AzureHDInsightJobDefinition
Parameter Sets: (All)
Aliases: jobDetails

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Subscription
Specifies a subscription.
This cmdlet starts a job for the subscription that this parameter specifies.

```yaml
Type: String
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases: Sub

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureHDInsightJob](./Get-AzureHDInsightJob.md)

[Get-AzureHDInsightJobOutput](./Get-AzureHDInsightJobOutput.md)

[New-AzureHDInsightMapReduceJobDefinition](./New-AzureHDInsightMapReduceJobDefinition.md)

[Stop-AzureHDInsightJob](./Stop-AzureHDInsightJob.md)

[Wait-AzureHDInsightJob](./Wait-AzureHDInsightJob.md)


