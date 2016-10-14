---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureHDInsightSqoopJobDefinition

## SYNOPSIS
Defines a new Sqoop job.

## SYNTAX

```
New-AzureHDInsightSqoopJobDefinition [-Command <String>] [-File <String>] [-Files <String[]>]
 [-StatusFolder <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of APS HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of APS HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using APS and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about APS HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **New-AzureHDInsightSqoopJobDefinition** cmdlet creates a Sqoop job to run on an azure_2 HDInsight cluster.

Sqoop is a tool to transfer data between Hadoop clusters and relational databases.
You can use Sqoop to import data from a ssNoVersion database to a Hadoop Distributed File System (HDFS), transform the data with Hadoop MapReduce, and then export the data from the HDFS back to the ssNoVersion database.

## EXAMPLES

### Example 1: Import data
```
PS C:\>$SqoopJobDef = New-AzureHDInsightSqoopJobDefinition -Command "import --connect jdbc:sqlserver://<SQLDatabaseServerName>.database.windows.net:1433;username=<SQLDatabasUsername>@<SQLDatabaseServerName>; password=<SQLDatabasePassword>; database=<SQLDatabaseDatabaseName> --table <TableName> --target-dir wasb://<ContainerName>@<WindowsAzureStorageAccountName>.blob.core.windows.net/<Path>"
```

This command defines a Sqoop job that imports all of the rows in a table from an azure_2ssNoVersion database to an HDInsight cluster, and then stores the job definition in the $SqoopJobDef variable.

## PARAMETERS

### -Command
Specifies a Sqoop command and its arguments.

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

### -File
Specifies the path to a script file that contains the commands to run.
The script file must be located on WASB.

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
Specifies the collection of WASB files that are required for a job.

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
ps_azureprofile_description

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

[New-AzureHDInsightHiveJobDefinition](.\New-AzureHDInsightHiveJobDefinition.md)

[New-AzureHDInsightMapReduceJobDefinition](.\New-AzureHDInsightMapReduceJobDefinition.md)

[New-AzureHDInsightPigJobDefinition](.\New-AzureHDInsightPigJobDefinition.md)

[New-AzureHDInsightStreamingMapReduceJobDefinition](.\New-AzureHDInsightStreamingMapReduceJobDefinition.md)

