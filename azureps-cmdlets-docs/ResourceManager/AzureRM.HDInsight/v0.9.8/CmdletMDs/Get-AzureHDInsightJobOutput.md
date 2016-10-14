---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: 773fd402-3dc5-41e9-b488-f41d46446618
schema: 2.0.0
---

# Get-AzureHDInsightJobOutput

## SYNOPSIS
Gets the log output for a job from the storage account associated with a specified cluster.

## SYNTAX

```
Get-AzureHDInsightJobOutput [-ResourceGroupName] <String> [-ClusterName] <String> [-JobId] <String>
 [-DefaultContainer] <String> [-DefaultStorageAccountName] <String> [-DefaultStorageAccountKey] <String>
 [-ClusterCredential] <PSCredential> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureHDInsightJobOutput** cmdlet gets the log output for a job from the storage account associated with a cluster.

## EXAMPLES

### Example 1: Get the log output for a job
```
PS C:\> # Cluster info
        $clusterResourceGroupName = "Group"
        $clusterName = "your-hadoop-001"
        $clusterCreds = Get-Credential

        # Hive job details
        $statusFolder = "<status folder>"
        $query = "<query here>"

        New-AzureHDInsightHiveJobDefinition -StatusFolder $statusFolder `
            -Query $query `
        | Start-AzureHDInsightJob -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds `
        | Get-AzureHDInsightJobOutput -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds 
 Get-AzureHDInsightJobOutput -ResourceGroupName "Group01" -ClusterName "Hadoop-001" -ClusterCredential Get-Credential
```

This command gets the log output from the cluster named Hadoop-001.

## PARAMETERS

### -ClusterCredential
The credentials with which to connect to the cluster.```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: 6
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

### -DefaultContainer
The default container name.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageAccountKey
The default storage account key.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageAccountName
The default storage account name.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Specifies the job ID of the job whose output will be fetched.

```yaml
Type: String
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

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

