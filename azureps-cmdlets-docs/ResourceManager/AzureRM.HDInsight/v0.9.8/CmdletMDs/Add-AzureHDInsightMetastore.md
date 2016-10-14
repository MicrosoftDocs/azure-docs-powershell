---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\New-AzureHDInsightCluster.md
schema: 2.0.0
---

# Add-AzureHDInsightMetastore

## SYNOPSIS
Adds a Hive or Oozie metastore to a cluster configuration object.

## SYNTAX

```
Add-AzureHDInsightMetastore [-Config] <AzureHDInsightConfig> [-MetastoreType] <AzureHDInsightMetastoreType>
 [-SqlAzureServerName] <String> [-DatabaseName] <String> [-Credential] <PSCredential> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureHDInsightMetastore** cmdlet adds a Hive or Oozie metastore to the HDInsight configuration object created by the New-AzureHDInsightClusterConfig cmdlet.
A metastore is a database that can used to store metadata for Hive or Oozie, or both.

## EXAMPLES

### Example 1: Add a metastore to the cluster configuration object.
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

This command adds a SQL database to the cluster named Hadoop-001.

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

### -Credential
Specifies the user credentials to use for the Azure SQL Server database.

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

### -DatabaseName
Specifies the database on the Azure SQL Server instance to use for this metastore.

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

### -MetastoreType
Specifies the type of metastore.
Possible values are HiveMetastore or OozieMetastore.

```yaml
Type: AzureHDInsightMetastoreType
Parameter Sets: (All)
Aliases: 
Accepted values: HiveMetastore, OozieMetastore

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

### -SqlAzureServerName
Specifies the Azure SQL Server instance to use for this metastore.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureHDInsightCluster](.\New-AzureHDInsightCluster.md)

[New-AzureHDInsightClusterConfig](.\New-AzureHDInsightClusterConfig.md)

[Azure HDInsight Cmdlets](.\AzureRM.HDInsight.md)

