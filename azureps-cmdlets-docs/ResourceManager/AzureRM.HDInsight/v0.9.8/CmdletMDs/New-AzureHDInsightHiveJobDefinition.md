---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\Invoke-AzureHDInsightHiveJob.md
schema: 2.0.0
---

# New-AzureHDInsightHiveJobDefinition

## SYNOPSIS
Creates a Hive job object.

## SYNTAX

```
New-AzureHDInsightHiveJobDefinition [-Arguments <String[]>] [-Files <String[]>] [-StatusFolder <String>]
 [-Defines <Hashtable>] [-File <String>] [-JobName <String>] [-Query <String>] [-RunAsFileJob]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureHDInsightHiveJobDefinition** cmdlet defines a Hive job object.

## EXAMPLES

### Example 1: Create a Hive job definition
```
PS C:\> # Cluster info
        $clusterResourceGroupName = "Group"
        $clusterName = "your-hadoop-001"
        $clusterCreds = Get-Credential

        # Hive job details
        $statusFolder = "tempStatusFolder/"
        $query = "SHOW TABLES"

        New-AzureHDInsightHiveJobDefinition -StatusFolder $statusFolder `
            -Query $query `
        | Start-AzureHDInsightJob -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds
```

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
Specifies Hadoop configuration values to set for when a job runs.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -File
Specifies the path to a file that contains a query to run.
You can use this parameter instead of the *Query* parameter.

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

### -Files
Specifies a collection of files that are associated with a Hive job.

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
Specifies the name of the Hive job to define.
If you do not specify this parameter, the default name is used: "Hive: \<first 100 characters of query\>".

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

### -Query
Specifies a Hive query.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Invoke-AzureHDInsightHiveJob](.\Invoke-AzureHDInsightHiveJob.md)

[New-AzureHDInsightCluster](.\New-AzureHDInsightCluster.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

