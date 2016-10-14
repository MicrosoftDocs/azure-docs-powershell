---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\New-AzureHDInsightCluster.md
schema: 2.0.0
---

# Add-AzureHDInsightScriptAction

## SYNOPSIS
Adds a script action to a cluster configuration object.

## SYNTAX

```
Add-AzureHDInsightScriptAction [-Config] <AzureHDInsightConfig> [-NodeType] <ClusterNodeType> [-Uri] <Uri>
 [-Name] <String> [-Parameters] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureHDInsightScriptAction** cmdlet provides Azure HDInsight functionality that is used to install additional software or to change the configuration of applications that run on a Hadoop cluster by using Windows PowerShell or Bash scripts (for Windows or Linux clusters, respectively).

A script action runs on the cluster nodes when HDInsight clusters are deployed, and they run after nodes in the cluster complete HDInsight configuration.
The script action runs under system administrator account privileges and provides full access rights to the cluster nodes.
You can provide each cluster with a list of script actions to run in a specified sequence.

## EXAMPLES

### Example 1: Add a script action to the cluster configuration object.
```
PS C:\> # Primary storage account info
        $storageAccountResourceGroupName = "Group"
        $storageAccountName = "yourstorageacct001"
        $storageAccountKey = Get-AzureStorageAccountKey `
            -ResourceGroupName $storageAccountResourceGroupName `
            -Name $storageAccountName | %{ $_.Key1 }
        $storageContainer = "container001"

        # Cluster configuration info
        $location = "East US 2"
        $clusterResourceGroupName = "Group"
        $clusterName = "your-hadoop-001"
        $clusterCreds = Get-Credential

        # If the cluster's resource group doesn't exist yet, run:
        #   New-AzureResourceGroup -Name $clusterResourceGroupName -Location $location

        # Hive metastore info
        $hiveSqlServer = "your-sqlserver-001"
        $hiveDb = "your-sqldb-001"
        $hiveCreds = Get-Credential

        # Oozie metastore info
        $oozieSqlServer = "your-sqlserver-001"
        $oozieDb = "your-sqldb-002"
        $oozieCreds = Get-Credential

        # Create the cluster
        New-AzureHDInsightClusterConfig  `
            | Add-AzureHDInsightStorage `
                -StorageAccountName "$secondStorageAccountName.blob.core.windows.net" `
                -StorageAccountKey $secondStorageAccountKey `
            | Add-AzureHDInsightMetastore `
                -SqlAzureServerName "$oozieSqlServer.database.windows.net" `
                -DatabaseName $oozieDb `
                -Credential $oozieCreds `
                -MetastoreType OozieMetastore `
            | Add-AzureHDInsightMetastore `
                -SqlAzureServerName "$hiveSqlServer.database.widows.net" `
                -DatabaseName $hiveDb `
                -Credential $hiveCreds `
                -MetastoreType HiveMetastore `
            | New-AzureHDInsightCluster `
                -ClusterType Hadoop `
                -OSType Windows `
                -ClusterSizeInNodes 4 `
                -ResourceGroupName $clusterResourceGroupName `
                -ClusterName $clusterName `
                -HttpCredential $clusterCreds `
                -Location $location `
                -DefaultStorageAccountName "$storageAccountName.blob.core.windows.net" `
                -DefaultStorageAccountKey $storageAccountKey `
                -DefaultStorageContainer $storageContainer
```

This command adds two action scripts to the cluster configuration named Hadoop-1.

## PARAMETERS

### -Config
Specifies the HDInsight cluster configuration object that this cmdlet modifies.

```yaml
Type: AzureHDInsightConfig
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the action.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeType
The node on which to apply the action.```yaml
Type: ClusterNodeType
Parameter Sets: (All)
Aliases: 
Accepted values: HeadNode, WorkerNode, ZookeeperNode

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Specifies the parameters for the action.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
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

### -Uri
Specifies the URI for the action.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

[New-AzureHDInsightClusterConfig](.\New-AzureHDInsightClusterConfig.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

