---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: .\Grant-AzureRmHDInsightHttpServicesAccess.md
schema: 2.0.0
---

# Revoke-AzureRmHDInsightHttpServicesAccess

## SYNOPSIS
Disables HTTP access to the cluster.

## SYNTAX

```
Revoke-AzureRmHDInsightHttpServicesAccess [-ClusterName] <String> [-ResourceGroupName <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-AzureRmHDInsightHttpServicesAccess** cmdlet disables HTTP access to an azure_2 HDInsight cluster for ODBC, Ambari, Oozie and webHCatalog web services.

## EXAMPLES

### Example 1: Disable HTTP access to a cluster
```
PS C:\>Revoke-AzureRmHDInsightHttpServicesAccess `
       -ClusterName "your-hadoop_001"
```

This command revokes HTTP access to the cluster named your-hadoop_001.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Grant-AzureRmHDInsightHttpServicesAccess](.\Grant-AzureRmHDInsightHttpServicesAccess.md)

