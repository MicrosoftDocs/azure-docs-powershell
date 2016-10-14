---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureHDInsightProperties

## SYNOPSIS
Gets properties specific to an HDInsight service.

## SYNTAX

```
Get-AzureHDInsightProperties [[-Certificate] <X509Certificate2>] [[-HostedService] <String>]
 [[-Endpoint] <Uri>] [-IgnoreSslErrors <Boolean>] [-Locations] [[-Subscription] <String>] [-Versions]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This version of Azure PowerShell HDInsight is deprecated.
These cmdlets will be removed by January 1, 2017.
Please use the newer version of Azure PowerShell HDInsight.

For information about how to use the new HDInsight to create a cluster, see Create Linux-based clusters in HDInsight using Azure PowerShellhttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/.
For information about how to submit jobs by using Azure PowerShell and other approaches, see Submit Hadoop jobs in HDInsighthttps://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/.
For reference information about Azure PowerShell HDInsight, see Azure HDInsight Cmdletshttps://msdn.microsoft.com/en-us/library/mt438705.aspx.

The **Get-AzureHDInsightProperties** cmdlet gets properties specific to an Azure HDInsight service, such as a list of available Azure regions, HDInsight cluster versions, and available compute capacity.

## EXAMPLES

### Example 1: Get HDInsight properties for a subscription
```
PS C:\>$SubName = Get-AzureSubscription -Current | %{ $_.SubscriptionName }
PS C:\> Get-AzureHDInsightProperties -Subscription $SubName
```

The first command gets the name of the current Azure subscription, and then stores it in the $SubName variable.

The second command gets the HDInsight properties for the subscription in $SubName.

## PARAMETERS

### -Certificate
Specifies the management certificate for an Azure subscription.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases: Cert

Required: False
Position: 2
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Endpoint
Specifies the endpoint to use to connect to Azure.
If you do not specify this parameter, this cmdlet uses the default endpoint.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Locations
Indicates that this cmdlet gets the list of Azure regions where the HDInsight service is available.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subscription
Specifies the subscription that contains the HDInsight properties to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Sub

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Versions
Indicates that this cmdlet gets the list of HDInsight cluster versions that are available in the service for a subscription.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
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

