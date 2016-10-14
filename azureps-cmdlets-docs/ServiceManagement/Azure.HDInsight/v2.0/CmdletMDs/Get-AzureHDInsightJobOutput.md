---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureHDInsightJobOutput

## SYNOPSIS
Gets the log output for a job.

## SYNTAX

```
Get-AzureHDInsightJobOutput [-Certificate <X509Certificate2>] [-HostedService <String>] [-Cluster] <String>
 [-DownloadTaskLogs] [-Endpoint <Uri>] [-IgnoreSslErrors <Boolean>] -JobId <String> [-StandardError]
 [-StandardOutput] [[-Subscription] <String>] [-TaskLogsDirectory <String>] [-TaskSummary]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **Get-AzureHDInsightJobOutput** cmdlet gets the log output for a job from the storage account associated with a cluster.
You can get various types of job logs including standard output, standard error, task logs, and a summary of the task logs.

## EXAMPLES

### Example 1: Get job output
```
PS C:\>$SubId = (Get-AzureSubscription  ¢â‚¬"Current).SubscriptionId
PS C:\> $ClusterName = "MyCluster" 
PS C:\> $WordCountJob = New-AzureHDInsightMapReduceJobDefinition -JarFile "/Example/Apps/Hadoop-examples.jar" -ClassName "Wordcount" -Defines @{ "mapred.map.tasks" = "3" } -Arguments "/Example/Data/Gutenberg/Davinci.txt", "/Example/Output/WordCount" $WordCountJob 
    | Start-AzureHDInsightJob -Subscription $SubId -Cluster $ClusterName 
    | Wait-AzureHDInsightJob -Subscription $SubId -WaitTimeoutInSeconds 3600 
    | Get-AzureHDInsightJobOutput -Cluster $ClusterName -StandardError
```

The first command gets the ID of the current subscription, and then stores it in the $SubId variable.

The second command stores the name MyCluster in the $Clustername variable.

The third command creates a MapReduce job definition, and then stores it in the $WordCountJob variable.
The command passes the job in $WordCountJob to the Start-AzureHDInsightJob cmdlet to start the job.
It also passes $WordCountJob to the Wait-AzureHDInsightJob cmdlet to wait for the job to finish, and then it uses **Get-AzureHDInsightJobOutput** to get the job output.

## PARAMETERS

### -Certificate
Specifies the management certificate for an Azure subscription.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases: Cert

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
Parameter Sets: (All)
Aliases: CloudServiceName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cluster
Specifies a cluster.
This cmdlet gets job logs from the cluster that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DownloadTaskLogs
Indicates that this cmdlet gets the task logs for a job.

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

### -Endpoint
Specifies the endpoint to use to connect to Azure.
If you do not specify this parameter, this cmdlet uses the default endpoint.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Specifies the ID of the job to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -StandardError
Indicates that this cmdlet gets the StdErr output of a job.

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

### -StandardOutput
Indicates that this cmdlet gets the SdtOut output of a job.

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

### -Subscription
Specifies the subscription that contains the HDInsight cluster to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Sub

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskLogsDirectory
Specifies a local folder in which to store tasks logs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LogsDir

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TaskSummary
Indicates that this cmdlets gets the task log summary.

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

### -IgnoreSslErrors
Indicates whether Secure Sockets Layer (SSL) errors are ignored.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureHDInsightMapReduceJobDefinition](.\New-AzureHDInsightMapReduceJobDefinition.md)

[Start-AzureHDInsightJob](.\Start-AzureHDInsightJob.md)

[Wait-AzureHDInsightJob](.\Wait-AzureHDInsightJob.md)

