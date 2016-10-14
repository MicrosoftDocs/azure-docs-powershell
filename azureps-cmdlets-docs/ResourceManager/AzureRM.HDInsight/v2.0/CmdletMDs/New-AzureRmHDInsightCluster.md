---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\Add-AzureRmHDInsightScriptAction.md
schema: 2.0.0
---

# New-AzureRmHDInsightCluster

## SYNOPSIS
Creates an Azure HDInsight cluster in the specified resource group for the current subscription.

## SYNTAX

### Default (Default)
```
New-AzureRmHDInsightCluster [-Location] <String> [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ClusterSizeInNodes] <Int32> [-HttpCredential] <PSCredential> [[-DefaultStorageAccountName] <String>]
 [[-DefaultStorageAccountKey] <String>] [-Config <AzureHDInsightConfig>]
 [-OozieMetastore <AzureHDInsightMetastore>] [-HiveMetastore <AzureHDInsightMetastore>]
 [-AdditionalStorageAccounts <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-Configurations <System.Collections.Generic.Dictionary`2[System.String,System.Collections.Generic.Dictionary`2[System.String,System.String]]>]
 [-ScriptActions <System.Collections.Generic.Dictionary`2[Microsoft.Azure.Management.HDInsight.Models.ClusterNodeType,System.Collections.Generic.List`1[Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightScriptAction]]>]
 [-DefaultStorageContainer <String>] [-Version <String>] [-HeadNodeSize <String>] [-WorkerNodeSize <String>]
 [-ZookeeperNodeSize <String>] [-ClusterType <String>] [-VirtualNetworkId <String>] [-SubnetName <String>]
 [-OSType <OSType>] [-ClusterTier <Tier>] [-SshCredential <PSCredential>] [-SshPublicKey <String>]
 [-RdpCredential <PSCredential>] [-RdpAccessExpiry <DateTime>] [-ObjectId <Guid>]
 [-CertificatePassword <String>] [-AadTenantId <Guid>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### CertificateFilePath
```
New-AzureRmHDInsightCluster [-Location] <String> [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ClusterSizeInNodes] <Int32> [-HttpCredential] <PSCredential> [[-DefaultStorageAccountName] <String>]
 [[-DefaultStorageAccountKey] <String>] [-Config <AzureHDInsightConfig>]
 [-OozieMetastore <AzureHDInsightMetastore>] [-HiveMetastore <AzureHDInsightMetastore>]
 [-AdditionalStorageAccounts <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-Configurations <System.Collections.Generic.Dictionary`2[System.String,System.Collections.Generic.Dictionary`2[System.String,System.String]]>]
 [-ScriptActions <System.Collections.Generic.Dictionary`2[Microsoft.Azure.Management.HDInsight.Models.ClusterNodeType,System.Collections.Generic.List`1[Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightScriptAction]]>]
 [-DefaultStorageContainer <String>] [-Version <String>] [-HeadNodeSize <String>] [-WorkerNodeSize <String>]
 [-ZookeeperNodeSize <String>] [-ClusterType <String>] [-VirtualNetworkId <String>] [-SubnetName <String>]
 [-OSType <OSType>] [-ClusterTier <Tier>] [-SshCredential <PSCredential>] [-SshPublicKey <String>]
 [-RdpCredential <PSCredential>] [-RdpAccessExpiry <DateTime>] [-ObjectId <Guid>]
 [-CertificateFilePath <String>] [-CertificatePassword <String>] [-AadTenantId <Guid>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### CertificateFileContents
```
New-AzureRmHDInsightCluster [-Location] <String> [-ResourceGroupName] <String> [-ClusterName] <String>
 [-ClusterSizeInNodes] <Int32> [-HttpCredential] <PSCredential> [[-DefaultStorageAccountName] <String>]
 [[-DefaultStorageAccountKey] <String>] [-Config <AzureHDInsightConfig>]
 [-OozieMetastore <AzureHDInsightMetastore>] [-HiveMetastore <AzureHDInsightMetastore>]
 [-AdditionalStorageAccounts <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-Configurations <System.Collections.Generic.Dictionary`2[System.String,System.Collections.Generic.Dictionary`2[System.String,System.String]]>]
 [-ScriptActions <System.Collections.Generic.Dictionary`2[Microsoft.Azure.Management.HDInsight.Models.ClusterNodeType,System.Collections.Generic.List`1[Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightScriptAction]]>]
 [-DefaultStorageContainer <String>] [-Version <String>] [-HeadNodeSize <String>] [-WorkerNodeSize <String>]
 [-ZookeeperNodeSize <String>] [-ClusterType <String>] [-VirtualNetworkId <String>] [-SubnetName <String>]
 [-OSType <OSType>] [-ClusterTier <Tier>] [-SshCredential <PSCredential>] [-SshPublicKey <String>]
 [-RdpCredential <PSCredential>] [-RdpAccessExpiry <DateTime>] [-ObjectId <Guid>]
 [-CertificateFileContents <Byte[]>] [-CertificatePassword <String>] [-AadTenantId <Guid>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmHDInsightCluster** creates an Azure HDInsight cluster by using the specified parameters or by using a configuration object that is created by using the New-AzureRmHDInsightClusterConfig cmdlet.

## EXAMPLES

### Example 1: Create an Azure HDInsight cluster
```
PS C:\># Primary storage account info
PS C:\> $storageAccountResourceGroupName = "Group"
PS C:\> $storageAccountName = "yourstorageacct001"
PS C:\> $storageAccountKey = (Get-AzureRmStorageAccountKey -ResourceGroupName $storageAccountResourceGroupName -Name $storageAccountName)[0].value


PS C:\>$storageContainer = "container002"

# Cluster configuration info
PS C:\>$location = "East US 2"
PS C:\>$clusterResourceGroupName = "Group"
PS C:\>$clusterName = "your-hadoop-002"
PS C:\>$clusterCreds = Get-Credential

# If the cluster's resource group doesn't exist yet, run:
#   New-AzureRmResourceGroup -Name $clusterResourceGroupName -Location $location

# Create the cluster
PS C:\>New-AzureRmHDInsightCluster `
            -ClusterType Hadoop `
            -OSType Windows `
            -ClusterSizeInNodes 4 `
            -ResourceGroupName $clusterResourceGroupName `
            -ClusterName $clusterName `
            -HttpCredential $clusterCreds `
            -Location $location `
            -DefaultStorageAccountName "$storageAccountName.blob.core.contoso.net" `
            -DefaultStorageAccountKey $storageAccountKey `
            -DefaultStorageContainer $storageContainer
```

This command creates a cluster in the current subscription.

## PARAMETERS

### -Location
Specifies the location for the cluster.

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

### -ResourceGroupName
Specifies the name of the resource group.

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

### -ClusterName
Specifies the name of the cluster.

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

### -ClusterSizeInNodes
Specifies the number of Worker nodes for the cluster.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpCredential
Specifies the cluster login (HTTP) credentials for the cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageAccountName
Specifies the default Storage account name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageAccountKey
Specifies the default Storage account key.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Config
Specifies the HDInsight cluster configuration object that this cmdlet modifies.
This object is created by the New-AzureRmHDInsightClusterConfig cmdlet.

```yaml
Type: AzureHDInsightConfig
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OozieMetastore
Specifies the SQL Database to store Oozie metadata.
You can alternatively use the Add-AzureRmHDInsightMetastore cmdlet.

```yaml
Type: AzureHDInsightMetastore
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HiveMetastore
Specifies the metastore to store Hive metadata.
You can alternatively use the Add-AzureRmHDInsightMetastore cmdlet.

```yaml
Type: AzureHDInsightMetastore
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdditionalStorageAccounts
Specifies the additional Azure Storage accounts for the cluster.
You can alternatively use the Add-AzureRmHDInsightStorage cmdlet.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Configurations
Specifies the configurations of this HDInsight cluster.
You can also use the Add-AzureRmHDInsightConfigValues cmdlet.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.Collections.Generic.Dictionary`2[System.String,System.String]]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptActions
Specifies the script actions to run on the cluster at the end of cluster creation.
You can alternatively use Add-AzureRmHDInsightScriptAction.

```yaml
Type: System.Collections.Generic.Dictionary`2[Microsoft.Azure.Management.HDInsight.Models.ClusterNodeType,System.Collections.Generic.List`1[Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightScriptAction]]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageContainer
Specifies the name of the default container in the default Azure storage account that the HDInsight cluster will use.
You can alternatively use the Set-AzureRmHDInsightDefaultStorage cmdlet.

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

### -Version
Specifies the HDI version of the HDInsight cluster.

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

### -HeadNodeSize
Specifies the size of the virtual machine for the Head node.
Use Get-AzureRmVMSize for acceptable VM sizes, and see HDInsight's pricing page.

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

### -WorkerNodeSize
Specifies the size of the virtual machine for the Worker node.
Use Get-AzureRMVMSize for acceptable virtual machine sizes, and see HDInsight's pricing page.

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

### -ZookeeperNodeSize
Specifies the size of the virtual machine for the Zookeeper node.
Use Get-AzureRMVMSize for acceptable virtual machine sizes, and see HDInsight's pricing page.
This parameter is valid only for HBase or Storm clusters.

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

### -ClusterType
Specifies the type of cluster to create.
The acceptable values for this parameter are:

- Hadoop
- HBase
- Storm
- Spark

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

### -VirtualNetworkId
Specifies the ID of the virtual network into which to provision the cluster.

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

### -SubnetName
Specifies the name of a subnet within the chosen virtual network for the cluster.

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

### -OSType
Specifies the operating system for the cluster.
The acceptable values for this parameter are:

- Windows
- Linux

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

### -ClusterTier
Specifies the HDInsight cluster tier.
By default, this is Standard.
The Premium tier can only be used with Linux clusters, and it enables the use of some new features.
The acceptable values for this parameter are:

- Standard
- Premium

```yaml
Type: Tier
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshCredential
Specifies the SSH credential to be used for SSH connections.
This is only for Linux clusters.

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
Specifies the public key to be used for SSH connections.
This is only for Linux clusters.

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

### -RdpCredential
Specifies the RDP credentials for the cluster.
This is only for Windows clusters.

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

### -ObjectId
Specifies the Azure AD object ID (a GUID) of the Azure AD Service Principal that represents the cluster.
The cluster will use this when accessing Azure Data Lake Store.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificatePassword
Specifies the password for the certificate that will be used to authenticate as the Service Principal.
The cluster will use this when accessing Azure Data Lake Store.

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

### -AadTenantId
Specifies the Azure AD Tenant ID that will be used when accessing Azure Data Lake Store.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateFilePath
Specifies the file path to the certificate that will be used to authenticate as the Service Principal.
The cluster will use this when accessing Azure Data Lake Store.

```yaml
Type: String
Parameter Sets: CertificateFilePath
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateFileContents
Specifies file contents of the certificate that will be used when accessing Azure Data Lake Store.

```yaml
Type: Byte[]
Parameter Sets: CertificateFileContents
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

[Add-AzureRmHDInsightScriptAction](.\Add-AzureRmHDInsightScriptAction.md)

[Add-AzureRmHDInsightStorage](.\Add-AzureRmHDInsightStorage.md)

[New-AzureRmHDInsightClusterConfig](.\New-AzureRmHDInsightClusterConfig.md)

