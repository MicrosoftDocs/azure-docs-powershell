---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\Get-AzureHDInsightJob.md
schema: 2.0.0
---

# Wait-AzureHDInsightJob

## SYNOPSIS
Waits for the completion or failure of a specified job and displays its progress

## SYNTAX

```
Wait-AzureHDInsightJob [-ResourceGroupName] <String> [-ClusterName] <String> [-JobId] <String>
 [-ClusterCredential] <PSCredential> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Wait-AzureHDInsightJob** cmdlet awaits the completion or failure of an Azure HDInsight job and displays the progress of the job.

## EXAMPLES

### Example 1: Wait for the completion or failure of a job and display its progress
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
        | Wait-AzureHDInsightJob -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds
```

## PARAMETERS

### -ClusterCredential
The credentials with which to connect to the cluster.```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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
Specifies the job ID of the job to wait for.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
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
The name of the resource group.```yaml
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

[Get-AzureHDInsightJob](.\Get-AzureHDInsightJob.md)

[New-AzureHDInsightHiveJobDefinition](.\New-AzureHDInsightHiveJobDefinition.md)

[Start-AzureHDInsightJob](.\Start-AzureHDInsightJob.md)

[Stop-AzureHDInsightJob](.\Stop-AzureHDInsightJob.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

