---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureHDInsightStorage

## SYNOPSIS
Adds a blob storage account entry to an HDInsight configuration.

## SYNTAX

```
Add-AzureHDInsightStorage [-Config] <AzureHDInsightConfig> [-StorageAccountKey] <String>
 [-StorageAccountName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **Add-AzureHDInsightStorage** cmdlet adds a blob storage account entry to an Azure HDInsight configuration.

## EXAMPLES

### Example 1: Add a storage account
```
PS C:\> $StoreConfig = Add-AzureHDInsightStorage -Config $Config -StorageAccountName "MyStorage" -StorageAccountKey "Key"
```

This command adds a storage account named MyStorage to the configuration object stored in $Config, and then stores the configuration in the $StoreConfig variable.

### Example 2: Configure multiple storage accounts
```
PS C:\> $SubId = (Get-AzureSubscription  ¢â‚¬"Current).SubscriptionId
PS C:\> $Key1 = Get-AzureStorageKey  ¢â‚¬"StorageAccountName "MyBlobStorage" | %{ $_.Primary }
PS C:\> $Key2 = Get-AzureStorageKey  ¢â‚¬"StorageAccountName "MySecondBlobStorage" | %{ $_.Primary }
PS C:\> $Creds = Get-Credential
PS C:\> $OozieCreds = Get-Credential
PS C:\> $HiveCreds = Get-Credential
PS C:\> New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4 
    | Set-AzureHDInsightDefaultStorage -StorageAccountName "MyBlobStorage.blob.core.windows.net" -StorageAccountKey $Key1 -StorageContainerName "MyContainer" 
    | Add-AzureHDInsightStorage -StorageAccountName "MySecondBlobStorage.blob.core.windows.net" -StorageAccountKey $Key2 
    | Add-AzureHDInsightMetastore -SqlAzureServerName "Sqlserver01.database.windows.net" -DatabaseName "MyOozieDatabaseName" -Credential $OozieCreds -MetastoreType OozieMetastore 
    | Add-AzureHDInsightMetastore -SqlAzureServerName "Sqlserver01.database.windows.net" -DatabaseName "MyHiveDatabaseName" -Credential $HiveCreds -MetastoreType HiveMetastore 
    | New-AzureHDInsightCluster -Subscription $SubID -Credential $Creds
```

The first command uses the **Get-AzureSubscription** cmdlet to get the current subscription ID, and then stores it in the $SubId variable.

The second and third commands use the Get-AzureStorageKey cmdlet to get the primary storage keys for MyBlobStorage and MySecondBlobStorage, and then store the keys in the $Key1 and $Key2 variables, respectively.

The fourth, fifth, and sixth commands get credentials for the current subscription and for Oozie and Hive, and then store the credentials in variables.

The final command performs a sequence of operations by using these cmdlets: 

 -- New-AzureHDInsightClusterConfig to create an HDInsight cluster configuration
- Set-AzureHDInsightDefaultStorage to set the default storage account for the configuration to MyBlobStorage.blob.core.windows.net
- **Add-AzureHDInsightStorage** to add a second storage account named MySecondBlobStorage.blob.core.windows.net to the configuration
- Add-AzureHDInsightStorage to add a metastore for Oozie and a metastore for Hive to the configuration
- New-AzureHDInsightCluster to create an HDInsight cluster with the new configuration

## PARAMETERS

### -Config
Specifies a configuration object.
This cmdlet adds storage account information to the object that this parameter specifies.

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

### -StorageAccountKey
Specifies the storage account key that is used to access a storage account.

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

### -StorageAccountName
Specifies the name of the Azure storage account to add.

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

