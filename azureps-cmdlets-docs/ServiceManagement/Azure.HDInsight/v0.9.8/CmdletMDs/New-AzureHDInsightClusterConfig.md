---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureHDInsightClusterConfig

## SYNOPSIS
Creates a non-persisted HDInsight cluster configuration.

## SYNTAX

```
New-AzureHDInsightClusterConfig [-ClusterSizeInNodes] <Int32> [[-HeadNodeVMSize] <String>]
 [[-ClusterType] <ClusterType>] [[-VirtualNetworkId] <String>] [[-SubnetName] <String>]
 [-DataNodeVMSize <String>] [-ZookeeperNodeVMSize <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **New-AzureHDInsightClusterConfig** cmdlet creates a non-persisted Azure HDInsight cluster configuration.

## EXAMPLES

### Example 1: Create a cluster configuration
```
PS C:\>$SubId = (Get-AzureSubscription -Current).SubscriptionId
PS C:\> $Key1 = Get-AzureStorageKey -StorageAccountName "MyBlobStorage" | %{ $_.Primary }
PS C:\> $Key2 = Get-AzureStorageKey -StorageAccountName "MySecondBlobStorage" | %{ $_.Primary }
PS C:\> $Creds = Get-Credential
PS C:\> $OozieCreds = Get-Credential
PS C:\> $HiveCreds = Get-Credential
PS C:\> New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4 
    | Set-AzureHDInsightDefaultStorage -StorageAccountName MyBlobStorage.blob.core.windows.net -StorageAccountKey $Key1 -StorageContainerName "MyContainer" 
    | Add-AzureHDInsightStorage -StorageAccountName "MySecondBlobStorage.blob.core.windows.net" -StorageAccountKey $Key2 
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.windows.net" -DatabaseName "MyOozieDatabaseName" -Credential $OozieCreds -MetastoreType OozieMetastore 
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.widows.net" -DatabaseName "MyHiveDatabaseName" -Credential $HiveCreds -MetastoreType HiveMetastore 
    | New-AzureHDInsightCluster -Subscription $SubID -Credential $Creds
```

The first command uses the **Get-AzureSubscription** cmdlet to get the current subscription ID, and then stores it in the $SubId variable.

The second and third commands use the Get-AzureStorageKey cmdlet to get the primary storage keys for MyBlobStorage and MySecondBlobStorage, and then store the keys in the $Key1 and $Key2 variables, respectively.

The fourth, fifth, and sixth commands use the **Get-Credential** cmdlet to get credentials for the current subscription and for Oozie and Hive, and then store the credentials in variables.

The final command performs a sequence of operations by using these cmdlets: 

 -- **New-AzureHDInsightClusterConfig** to create an HDInsight cluster configuration.
- Set-AzureHDInsightDefaultStorage to set the default storage account for the configuration to MyBlobStorage.blob.core.windows.net.
- Add-AzureHDInsightStorage to add a second storage account named MySecondBlobStorage.blob.core.windows.net to the configuration.
- Add-AzureHDInsightMetastore to add a metastore for Oozie and a metastore for Hive to the configuration.
- New-AzureHDInsightCluster to create an HDInsight cluster with the new configuration.

## PARAMETERS

### -ClusterSizeInNodes
Specifies the number of data nodes to create for a cluster.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: Nodes, Size

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeadNodeVMSize
Specifies the VM size of the head node for the cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterType
Specifies the type of cluster to create.

```yaml
Type: ClusterType
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkId
Specifies the ID of the virtual network into which to provision the cluster.

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

### -SubnetName
Specifies the name of a subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataNodeVMSize
Specifies the size of the virtual machine (VM) for the data node.

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

### -Profile
Specifies an Azure profile.
If you do not specify this parameter, this cmdlet uses the local default profile.

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

### -ZookeeperNodeVMSize
Specifies the size of the VM for the ZooKeeper node for an HBase or Storm cluster.

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

[Add-AzureHDInsightMetastore](.\Add-AzureHDInsightMetastore.md)

[Add-AzureHDInsightStorage](.\Add-AzureHDInsightStorage.md)

[New-AzureHDInsightCluster](.\New-AzureHDInsightCluster.md)

[Set-AzureHDInsightDefaultStorage](.\Set-AzureHDInsightDefaultStorage.md)

