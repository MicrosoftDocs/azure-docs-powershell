---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\New-AzureHDInsightCluster.md
schema: 2.0.0
---

# Get-AzureHDInsightCluster

## SYNOPSIS
Gets and lists all of the Azure HDInsight clusters associated with the current subscription or a specified resource group, or retrieves a specific cluster.

## SYNTAX

```
Get-AzureHDInsightCluster [[-ResourceGroupName] <String>] [[-ClusterName] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureHDInsightCluster** cmdlet gets the Azure HDInsight service clusters for the current subscription.
You can use the *ClusterName* and *ResourceGroupName* parameters to get a specific cluster.

## EXAMPLES

### Example 1: List all Azure HDInsight clusters
```
PS C:\>Get-AzureHDInsightCluster
```

This command gets all the Azure HDInsight clusters.

## PARAMETERS

### -ClusterName
Gets or sets the name of the cluster.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

Required: False
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

[New-AzureHDInsightCluster](.\New-AzureHDInsightCluster.md)

[Remove-AzureHDInsightCluster](.\Remove-AzureHDInsightCluster.md)

[Use-AzureHDInsightCluster](.\Use-AzureHDInsightCluster.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

