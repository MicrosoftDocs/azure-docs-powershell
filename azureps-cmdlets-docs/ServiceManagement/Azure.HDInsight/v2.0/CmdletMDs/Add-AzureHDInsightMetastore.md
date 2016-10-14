---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureHDInsightMetastore

## SYNOPSIS
Adds a SQL Server database account to an HDInsight cluster configuration.

## SYNTAX

```
Add-AzureHDInsightMetastore [-Config] <AzureHDInsightConfig> [-Credential] <PSCredential>
 [-DatabaseName] <String> [-MetastoreType] <AzureHDInsightMetastoreType> [-SqlAzureServerName] <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **Add-AzureHDInsightMetastore** cmdlet adds a Microsoft SQL Server database to an Azure HDInsight configuration that is created by the New-AzureHDInsightClusterConfig cmdlet.
The database is used to store metadata for Hive or Oozie, or both.

## EXAMPLES

### Example 1: Add a metastore
```
PS C:\>$Metaconfig = Add-AzureHDInsightMetastore -Config $Config -SqlAzureServerName "ContosoSQLServer" -DatabaseName "DBname" -Credential (Get-Credential) -MetastoreType HiveMetaStore
```

This command adds a SQL Server database named ContosoSQLServer to serve as a Hive metastore for an HDInsight cluster.

### Example 2: Configure storage and add metastores
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
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.widows.net" -DatabaseName "MyHiveDatabaseName" -Credential $HiveCreds -MetastoreType HiveMetastore 
    | New-AzureHDInsightCluster -Subscription $SubId -Credential $Creds
```

The first command uses the Get-AzureSubscription cmdlet to get the current subscription ID, and then stores it in the $SubId variable.

The second and third commands use the Get-AzureStorageKey cmdlet to get the primary storage keys for MyBlobStorage and MySecondBlobStorage, and then store the keys in the $Key1 and $Key2 variables, respectively.

The fourth, fifth, and sixth commands use the Get-Credential cmdlet to get credentials for the current subscription and for Oozie and Hive, and then store the credentials in variables.

The final command performs a sequence of operations by using these cmdlets: 

 -- New-AzureHDInsightClusterConfig to create an HDInsight cluster configuration.
- Set-AzureHDInsightDefaultStorage to set the default storage account for the configuration to MyBlobStorage.blob.core.windows.net.
- Add-AzureHDInsightStorage to add a second storage account named MySecondBlobStorage.blob.core.windows.net to the configuration.
- **Add-AzureHDInsightMetastore** to add a metastore for Oozie and a metastore for Hive to the configuration.
- New-AzureHDInsightCluster to create an HDInsight cluster with the new configuration.

## PARAMETERS

### -Config
Specifies a configuration object.
This cmdlet adds metastore information to the configuration object that this parameter specifies.

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

### -Credential
Specifies the credentials that are used to access a SQL Server database.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database to store Hive or Oozie metadata.

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

### -MetastoreType
Specifies the metastore type.
The acceptable values for this parameter are: HiveMetaStore or OozieMetaStore.

```yaml
Type: AzureHDInsightMetastoreType
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlAzureServerName
Specifies the fully qualified domain name (FQDN) of the SQL Server that contains the database to store metadata.

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
Type: AzureSMProfile
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

[Add-AzureHDInsightStorage](.\Add-AzureHDInsightStorage.md)

[New-AzureHDInsightCluster](.\New-AzureHDInsightCluster.md)

[New-AzureHDInsightClusterConfig](.\New-AzureHDInsightClusterConfig.md)

[Set-AzureHDInsightDefaultStorage](.\Set-AzureHDInsightDefaultStorage.md)

