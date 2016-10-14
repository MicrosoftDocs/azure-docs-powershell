---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureHDInsightConfigValues

## SYNOPSIS
Adds a Hadoop configuration value customization or a Hive shared library customization to an HDInsight cluster configuration.

## SYNTAX

```
Add-AzureHDInsightConfigValues [-Config] <AzureHDInsightConfig> [-Core <Hashtable>] [-Yarn <Hashtable>]
 [-Hdfs <Hashtable>] [-Hive <AzureHDInsightHiveConfiguration>]
 [-MapReduce <AzureHDInsightMapReduceConfiguration>] [-Oozie <AzureHDInsightOozieConfiguration>]
 [-Storm <Hashtable>] [-Spark <Hashtable>] [-HBase <AzureHDInsightHBaseConfiguration>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **Add-AzureHDInsightConfigValues** cmdlet adds a Hadoop configuration value customization, such as Core-site.xml or Hive-site.xml, or a Hive shared library customization to an Azure HDInsight cluster configuration.

The cmdlet adds custom configuration values to a specified configuration object.
The custom settings are added to the configuration files of the relevant Hadoop services when the cluster is deployed.

## EXAMPLES

### Example 1: Configure a cluster
```
PS C:\>$HiveConfigValues = New-Object 'Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.DataObjects.AzureHDInsightHiveConfiguration'
PS C:\> $HiveConfigValues.Configuration = @{ hive.exec.compress.output = true }
PS C:\> $HiveConfigValues.AdditionalLibraries = New-Object 'Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.DataObjects.AzureHDInsightDefaultStorageAccount'
PS C:\> $HiveConfigValues.AdditionalLibraries.StorageAccountName = "MyStorageAccount.blob.core.windows.net" 
PS C:\> $HiveConfigValues.AdditionalLibraries.StorageAccountKey = (Get-AzureStorageKey -StorageAccountName "MyStorageAccount").Primary 
PS C:\> $HiveConfigValues.AdditionalLibraries.StorageContainerName = "MySharedLibContainer"
PS C:\> $OozieConfigValues = New-Object 'Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.DataObjects.AzureHDInsightOozieConfiguration'
PS C:\> $OozieConfigValues.Configuration = @{ hive.exec.compress.output = true }
PS C:\> $MapredConfigValues = New-Object 'Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.DataObjects.AzureHDInsightMapReduceConfiguration'
PS C:\> $MapredConfigValues.Configuration = @{ mapred.map.max.attempts = 2 }
PS C:\> $MapredConfigValues.CapacitySchedulerConfiguration = @{ mapred.capacity-scheduler.init-poll-interval = 1000 }
PS C:\> $Config = New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4 
    | Set-AzureHDInsightDefaultStorage -StorageAccountName MyStorageAccount.blob.core.windows.net -StorageAccountKey (Get-AzureStorageKey -StorageAccountName "MyStorageAccount").Primary -StorageContainerName "MyStorageContainer" 
    | Add-AzureHDInsightConfigValues -Core @{ io.file.buffer.size = 300000 } -MapReduce $MapredConfigValues -Hive $HiveConfigValues -Oozie $OozieConfigValues
PS C:\> $Config | New-AzureHDInsightCluster -Subscription $SubId -Credential $Creds -Name "MyCluster" -Location "North Europe"
```

The first command creates a new **AzureHDInsightHiveConfiguration** object, and then stores it in the $HiveConfigValues variable.
The next five commands create configuration values for Hive and store those values as members of $HiveConfigValues.

The seventh command creates an **AzureHDInsightOozieConfiguration** object, and then stores it in the $OozieConfigValues variable.
The eighth command creates a configuration value for Oozie, and then stores that values as a member of $OozieConfigValues.

The ninth command creates an **AzureHDInsightMapReduceConfiguration** object, and then stores it in the $MapredConfigValues variable.
The next two commands create configuration values for MapReduce and store those values as members of $MapredConfigValues.

The twelfth command uses the New-AzureHDInsightClusterConfig cmdlet to create an HDInsight cluster configuration, and then stores it in the $Config variable.
The command uses the pipeline operator to pass $Config to the Set-AzureHDInsightDefaultStorage cmdlet to update the default storage setting and to the **Add-AzureHDInsightConfigValues** cmdlet to add the new configuration values to the cluster configuration.

The final command uses the pipeline operator to pass $Config to the New-AzureHDInsightCluster cmdlet to create a new HDInsight cluster with the customized settings.

## PARAMETERS

### -Config
Specifies the configuration object to which to add a Hadoop configuration.

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

### -Core
Specifies a set of Hadoop configuration values for Core-site.xml.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Yarn
Specifies a customization object for Hadoop YARN, specifying a set of customized YARN configuration values for Yarn-site.xml.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hdfs
Specifies a set of Hadoop configuration values for Hdfs-site.xml.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hive
Specifies a customization object for Hadoop Hive service, including a set of Hadoop configuration values for Hive-site.xml and Hive shared libraries.

```yaml
Type: AzureHDInsightHiveConfiguration
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MapReduce
Specifies a customization object for MapReduce and the capacity scheduler.

```yaml
Type: AzureHDInsightMapReduceConfiguration
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Oozie
Specifies a customization object for Hadoop Oozie service, including a set of Hadoop configuration values for Oozie-site.xml.

```yaml
Type: AzureHDInsightOozieConfiguration
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storm
Specifies a customization object for Apache Storm.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HBase
Specifies a set of HBase configuration values for Hbase-site.xml.

```yaml
Type: AzureHDInsightHBaseConfiguration
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

### -Spark
Specifies a customization object for Apache Spark.

```yaml
Type: Hashtable
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

[New-AzureHDInsightCluster](.\New-AzureHDInsightCluster.md)

[New-AzureHDInsightClusterConfig](.\New-AzureHDInsightClusterConfig.md)

[Set-AzureHDInsightDefaultStorage](.\Set-AzureHDInsightDefaultStorage.md)

