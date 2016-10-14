---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\Revoke-AzureHDInsightHttpServicesAccess.md
schema: 2.0.0
---

# Grant-AzureHDInsightHttpServicesAccess

## SYNOPSIS
Grants HTTP access to a cluster.

## SYNTAX

```
Grant-AzureHDInsightHttpServicesAccess [-ResourceGroupName] <String> [-ClusterName] <String>
 [-HttpCredential] <PSCredential> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-AzureHDInsightHttpServicesAccess** cmdlet grants HTTP access to an Azure HDInsight cluster.

## EXAMPLES

### Example 1: Grant HTTP access to an Azure HDInsight cluster
```
PS C:\> # Cluster info
        $clusterResourceGroupName = "Group"
        $clusterName = "your-hadoop-001"
        $clusterCreds = Get-Credential
        
        Grant-AzureHDInsightHttpServicesAccess -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName `
            -HttpCredential $newClusterCreds
```

This command grants HTTP access to the cluster named Hadoop-001.

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

### -HttpCredential
Gets or sets the login for the cluster's user.```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

[Revoke-AzureHDInsightHttpServicesAccess](.\Revoke-AzureHDInsightHttpServicesAccess.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

