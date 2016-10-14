---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\Grant-AzureHDInsightRdpServicesAccess.md
schema: 2.0.0
---

# Revoke-AzureHDInsightRdpServicesAccess

## SYNOPSIS
Disables RDP access to a cluster.

## SYNTAX

```
Revoke-AzureHDInsightRdpServicesAccess [-ResourceGroupName] <String> [-ClusterName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-AzureHDInsightRdpServicesAccess** cmdlet disables Remote Desktop Protocol (RDP) access to a cluster.

## EXAMPLES

### Example 1: Disable RDP access to a specified cluster
```
PS C:\> # Cluster info
        $clusterResourceGroupName = "Group"
        $clusterName = "your-hadoop-001"

        Revoke-AzureHDInsightRdpServicesAccess `
            -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName
```

## PARAMETERS

### -ClusterName
Specifies the name of the cluster.

```yaml
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
Specifies the name of the resource group.

```yaml
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

[Grant-AzureHDInsightRdpServicesAccess](.\Grant-AzureHDInsightRdpServicesAccess.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

