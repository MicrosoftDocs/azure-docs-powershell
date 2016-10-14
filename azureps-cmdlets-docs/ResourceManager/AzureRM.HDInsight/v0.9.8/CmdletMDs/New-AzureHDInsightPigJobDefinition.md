---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: https://azure.microsoft.com/en-us/documentation/articles/hdinsight-use-pig/
schema: 2.0.0
---

# New-AzureHDInsightPigJobDefinition

## SYNOPSIS
Creates a pig job object.

## SYNTAX

```
New-AzureHDInsightPigJobDefinition [-Arguments <String[]>] [-Files <String[]>] [-StatusFolder <String>]
 [-File <String>] [-Query <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureHDInsightPigJobDefinition** cmdlet defines a Pig job object.
For more information regarding Pig jobs, see Use Pig with Hadoop on HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-use-pig/

## EXAMPLES

### Example 1: Create a Pig job definition
```
PS C:\> # Cluster info
        $clusterResourceGroupName = "Group"
        $clusterName = "your-hadoop-001"
        $clusterCreds = Get-Credential

        # Pig job details
        $statusFolder = "tempStatusFolder/"
        $query = "SHOW TABLES"

        New-AzureHDInsightPigJobDefinition -StatusFolder $statusFolder `
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
Specifies a collection of files that are associated with a Pig job.

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
Specifies a Pig job query.

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

[Use Pig with Hadoop on HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-use-pig/)

[Start-AzureHDInsightJob](.\Start-AzureHDInsightJob.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

