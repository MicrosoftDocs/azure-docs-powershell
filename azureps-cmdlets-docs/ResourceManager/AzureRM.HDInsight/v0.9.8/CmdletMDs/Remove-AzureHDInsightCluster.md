---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\Get-AzureHDInsightCluster.md
schema: 2.0.0
---

# Remove-AzureHDInsightCluster

## SYNOPSIS
Deletes the specified HDInsight cluster from the current subscription.

## SYNTAX

```
Remove-AzureHDInsightCluster [-ResourceGroupName] <String> [-ClusterName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureHDInsightCluster** cmdlet deletes the specified HDInsight service cluster from a subscription.
This operation also deletes any data stored in the Hadoop Distributed File System (HDFS) on the cluster.
Data stored in the associated Azure Storage account is not deleted.
Data stored in external metastores is not deleted.

## EXAMPLES

### Example 1: Delete an Azure HDInsight cluster.
```
PS C:\> # Cluster info
        $clusterResourceGroupName = "Group"
        $clusterName = "your-hadoop-001"

        Remove-AzureHDInsightCluster -ResourceGroupName $clusterResourceGroupName `
                -ClusterName $clusterName
```

## PARAMETERS

### -ClusterName
Gets or sets the name of the cluster.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

[Get-AzureHDInsightCluster](.\Get-AzureHDInsightCluster.md)

[New-AzureHDInsightCluster](.\New-AzureHDInsightCluster.md)

[Use-AzureHDInsightCluster](.\Use-AzureHDInsightCluster.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

