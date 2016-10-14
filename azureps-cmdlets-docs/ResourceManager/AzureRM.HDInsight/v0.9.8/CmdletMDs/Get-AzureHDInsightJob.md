---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\Start-AzureHDInsightJob.md
schema: 2.0.0
---

# Get-AzureHDInsightJob

## SYNOPSIS
Gets the list of jobs from a cluster and lists them in reverse chronological order, or retrieves a specific job.

## SYNTAX

```
Get-AzureHDInsightJob [-ResourceGroupName] <String> [-ClusterName] <String> [-ClusterCredential] <PSCredential>
 [[-JobId] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureHDInsightJob** cmdlet gets recent jobs for a specified cluster in reverse chronological order, with the most recent job at the top of the list.
You can get a specific job by providing the *JobId* parameter.

## EXAMPLES

### Example 1: Get recent jobs for a specified Azure HDInsight cluster
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
            -ClusterCredential $clusterCreds `
        | Get-AzureHDInsightJob -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds
```

This command gets all recent jobs for the cluster named Hadoop-001.

## PARAMETERS

### -ClusterCredential
The credentials with which to connect to the cluster.```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName
The name of the cluster.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Specifies the job ID of the jobDetails to stop.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### -ResourceGroupName
Gets or sets the name of the resource group.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Start-AzureHDInsightJob](.\Start-AzureHDInsightJob.md)

[Stop-AzureHDInsightJob](.\Stop-AzureHDInsightJob.md)

[Wait-AzureHDInsightJob](.\Wait-AzureHDInsightJob.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

