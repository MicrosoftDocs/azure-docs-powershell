---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureHDInsightCluster

## SYNOPSIS
Creates an HDInsight cluster.

## SYNTAX

### Cluster By Config (with Specific Subscription Credential) (Default)
```
New-AzureHDInsightCluster [[-Certificate] <X509Certificate2>] [[-HostedService] <String>]
 [-Config] <AzureHDInsightConfig> [-Credential] <PSCredential> [[-EndPoint] <Uri>] [-IgnoreSslErrors <Boolean>]
 [-Location] <String> [-Name] <String> [[-Subscription] <String>] [[-Version] <String>] [-OSType <OSType>]
 [-SshCredential <PSCredential>] [-SshPublicKey <String>] [-RdpCredential <PSCredential>]
 [-RdpAccessExpiry <DateTime>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Cluster By Name (with Specific Subscription Credential)
```
New-AzureHDInsightCluster [[-Certificate] <X509Certificate2>] [[-HostedService] <String>]
 [-ClusterSizeInNodes] <Int32> [-Credential] <PSCredential> [-DefaultStorageAccountKey] <String>
 [-DefaultStorageAccountName] <String> [-DefaultStorageContainerName] <String> [[-EndPoint] <Uri>]
 [-IgnoreSslErrors <Boolean>] [-Location] <String> [-Name] <String> [[-Subscription] <String>]
 [[-Version] <String>] [[-HeadNodeVMSize] <String>] [[-ClusterType] <ClusterType>]
 [[-VirtualNetworkId] <String>] [[-SubnetName] <String>] [-DataNodeVMSize <String>]
 [-ZookeeperNodeVMSize <String>] [-OSType <OSType>] [-SshCredential <PSCredential>] [-SshPublicKey <String>]
 [-RdpCredential <PSCredential>] [-RdpAccessExpiry <DateTime>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **New-AzureHDInsightCluster** cmdlet creates an Azure HDInsight cluster by using the specified parameters or by using a configuration object that is created by using the New-AzureHDInsightClusterConfig cmdlet.

## EXAMPLES

### Example 1: Create an HDInsight cluster
```
PS C:\>$SubId = (Get-AzureSubscription -Current).SubscriptionId
PS C:\> $Key1 = Get-AzureStorageKey -StorageAccountName "MyBlobStorage" | %{ $_.Primary }
PS C:\> $Key2 = Get-AzureStorageKey -StorageAccountName "MySecondBlobStorage" | %{ $_.Primary }
PS C:\> $Creds = Get-Credential
PS C:\> $OozieCreds = Get-Credential
PS C:\> $HiveCreds = Get-Credential 
PS C:\> New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4 
    | Set-AzureHDInsightDefaultStorage -StorageAccountName "MyBlobStorage.blob.core.windows.net" -StorageAccountKey $Key1 -StorageContainerName "MyContainer" 
    | Add-AzureHDInsightStorage -StorageAccountName "MySecondBlobStorage.blob.core.windows.net" -StorageAccountKey $Key2 
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.windows.net" -DatabaseName "MyOozieDatabaseName" -Credential $OozieCreds -MetastoreType OozieMetastore 
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.windows.net" -DatabaseName "MyHiveDatabaseName" -Credential $HiveCreds -MetastoreType HiveMetastore 
    | New-AzureHDInsightCluster -Subscription $SubId -Credential $Creds
```

This example creates an HDInsight cluster for the current subscription.

The first command uses the Get-AzureSubscription cmdlet to get the current subscription ID, and then stores it in the $SubId variable.

The second and third commands use the Get-AzureStorageKey cmdlet to get the primary storage keys for MyBlobStorage and MySecondBlobStorage, and then store the keys in the $Key1 and $Key2 variables, respectively.

The fourth, fifth, and sixth commands use the Get-Credential cmdlet to get credentials for the current subscription and for Oozie and Hive, and then store the credentials in variables.

The final command performs a sequence of operations by using these cmdlets:

- New-AzureHDInsightClusterConfig to create an HDInsight cluster configuration.
- Set-AzureHDInsightDefaultStorage to set the default storage account for the configuration to MyBlobStorage.blob.core.windows.net.
- Add-AzureHDInsightStorage to add a second storage account named MySecondBlobStorage.blob.core.windows.net to the configuration.
- Add-AzureHDInsightMetastore to add a metastore for Oozie and a metastore for Hive to the configuration.
- **New-AzureHDInsightCluster** to create an HDInsight cluster with the new configuration.

## PARAMETERS

### -Certificate
Specifies the management certificate for an Azure subscription.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases: Cert

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostedService
Specifies the namespace of an HDInsight service.
If you do not specify this parameter, this cmdlet uses the default namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CloudServiceName

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Config
Specifies a configuration object that is created by using the **New-AzureHDInsightClusterConfig** cmdlet.

```yaml
Type: AzureHDInsightConfig
Parameter Sets: Cluster By Config (with Specific Subscription Credential)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies the user credentials for HDInsight to use for the default account that is used to remotely access a Hadoop cluster.
These credentials are distinct from the subscription credentials of the user.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: Cred

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndPoint
Specifies the endpoint to use to connect to Azure.
If you do not specify this parameter, this cmdlet uses the default endpoint.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the region in which to create an HDInsight cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Loc

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the Azure HDInsight cluster to create.

```yaml
Type: String
Parameter Sets: Cluster By Config (with Specific Subscription Credential)
Aliases: ClusterName, DnsName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: ClusterName, DnsName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subscription
Specifies the Azure subscription in which to create an HDInsight cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Sub

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the HDInsight cluster version to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Ver

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterSizeInNodes
Specifies the number of data nodes to create for a cluster.

```yaml
Type: Int32
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: Nodes, Size

Required: True
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageAccountKey
Specifies the account key for the default storage account that the HDInsight cluster uses.

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: StorageKey

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageAccountName
Specifies the name of the default storage account that the HDInsight cluster uses.

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: StorageAccount

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageContainerName
Specifies the name of the default container in the default Azure storage account that an HDInsight cluster uses.

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: StorageContainer

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeadNodeVMSize
Specifies the size of the virtual machine for the head node.

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: 

Required: False
Position: 13
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterType
Specifies the type of cluster to create.

```yaml
Type: ClusterType
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: 

Required: False
Position: 14
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkId
Specifies the ID of the virtual network into which to provision the cluster.

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: 

Required: False
Position: 15
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Specifies the name of a subnet.

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: 

Required: False
Position: 16
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataNodeVMSize
Specifies the size of the virtual machine for the data node.

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreSslErrors
Indicates whether Secure Sockets Layer (SSL) errors are ignored.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSType
Specifies the operating system for a cluster.

```yaml
Type: OSType
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RdpAccessExpiry
Specifies the expiration, as a **DateTime** object, for Remote Desktop Protocol (RDP) access to a cluster.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RdpCredential
Specifies the credentials for RDP access to a cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshCredential
Specifies the Secure Shell (SSH) user name and password for the HDInsight cluster.
This parameter is valid only for Linux clusters.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshPublicKey
Specifies the SSH public key for an HDInsight cluster.
This parameter is valid only for Linux clusters.

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

### -ZookeeperNodeVMSize
Specifies the size of the virtual machine for the ZooKeeper node.
This parameter is valid only for HBase or Storm clusters.

```yaml
Type: String
Parameter Sets: Cluster By Name (with Specific Subscription Credential)
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

[Get-AzureHDInsightCluster](.\Get-AzureHDInsightCluster.md)

[New-AzureHDInsightClusterConfig](.\New-AzureHDInsightClusterConfig.md)

[Remove-AzureHDInsightCluster](.\Remove-AzureHDInsightCluster.md)

[Set-AzureHDInsightDefaultStorage](.\Set-AzureHDInsightDefaultStorage.md)

[Use-AzureHDInsightCluster](.\Use-AzureHDInsightCluster.md)

