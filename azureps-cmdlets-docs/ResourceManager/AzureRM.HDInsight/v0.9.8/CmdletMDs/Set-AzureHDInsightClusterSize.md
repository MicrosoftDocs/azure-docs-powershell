---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: 773fd402-3dc5-41e9-b488-f41d46446618
schema: 2.0.0
---

# Set-AzureHDInsightClusterSize

## SYNOPSIS
Sets the size of a specified cluster.

## SYNTAX

```
Set-AzureHDInsightClusterSize [-ResourceGroupName] <String> [-ClusterName] <String>
 [-TargetInstanceCount] <Int32> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureHDInsightClusterSize** cmdlet sets the number of worker nodes for the specified cluster.

## EXAMPLES

### Example 1: Set the size of a specified cluster
```
PS C:\> # Cluster info
        $clusterResourceGroupName = "Group"
        $clusterName = "your-hadoop-001"

        Set-AzureHDInsightClusterSize -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName `
            -TargetInstanceCount 6
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

### -TargetInstanceCount
Gets or sets the name of the cluster.```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

