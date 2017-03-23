---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmHDInsightJobOutput

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### Display
```
Get-AzureRmHDInsightJobOutput [-ClusterName] <String> [-JobId] <String> [-DefaultContainer] <String>
 [-DefaultStorageAccountName] <String> [-DefaultStorageAccountKey] <String> [-HttpCredential] <PSCredential>
 [-ResourceGroupName <String>] [-DisplayOutputType <JobDisplayOutputType>] [<CommonParameters>]
```

### Download
```
Get-AzureRmHDInsightJobOutput [-ClusterName] <String> [-JobId] <String> [-DefaultContainer] <String>
 [-DefaultStorageAccountName] <String> [-DefaultStorageAccountKey] <String> [-HttpCredential] <PSCredential>
 [-ResourceGroupName <String>] -DownloadOutputType <JobDownloadOutputType> -Folder <String>
 [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ClusterName
The name of the cluster.

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

### -DefaultContainer
The default container name.

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

### -DefaultStorageAccountKey
The default storage account key.

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

### -DefaultStorageAccountName
The default storage account name.

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

### -DisplayOutputType
The type of job output.

```yaml
Type: JobDisplayOutputType
Parameter Sets: Display
Aliases: 
Accepted values: StandardOutput, StandardError, TaskSummary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DownloadOutputType
The type of output to download.

```yaml
Type: JobDownloadOutputType
Parameter Sets: Download
Aliases: 
Accepted values: TaskLogs

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Folder
The folder to save the output to.

```yaml
Type: String
Parameter Sets: Download
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpCredential
The credentials with which to connect to the cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: ClusterCredential

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
The JobID of the jobDetails to stop.

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

### -ResourceGroupName
Gets or sets the name of the resource group.

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

### None

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

