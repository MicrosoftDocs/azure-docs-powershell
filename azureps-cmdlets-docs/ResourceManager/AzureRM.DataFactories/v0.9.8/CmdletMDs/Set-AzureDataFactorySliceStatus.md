---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 7a828f4d-bcad-4c9a-8a41-ea9bedde2552
schema: 2.0.0
---

# Set-AzureDataFactorySliceStatus

## SYNOPSIS
Sets the status of slices for a dataset in an Azure data factory.

## SYNTAX

### ByFactoryName (Default)
```
Set-AzureDataFactorySliceStatus [[-EndDateTime] <DateTime>] [-Status] <String> [[-UpdateType] <String>]
 [-DataFactoryName] <String> [-DatasetName] <String> [-StartDateTime] <DateTime> [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
Set-AzureDataFactorySliceStatus [[-EndDateTime] <DateTime>] [-Status] <String> [[-UpdateType] <String>]
 [-DataFactory] <PSDataFactory> [-DatasetName] <String> [-StartDateTime] <DateTime> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureDataFactorySliceStatus** cmdlet sets the status of slices for a dataset in an Azure data factory.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Set-AzureDataFactorySliceStatus -ResourceGroupName "ADF" -DataFactoryName :"WikiADF" -DatasetName "DAWikiAggregatedData" -Status Waiting -UpdateType UpstreamInPipeline -StartDateTime 2014-05-21T16:00:00 -EndDateTime 2014-05-21T20:00:00
```

Sets the status of all slices for the dataset DAWikiAggregatedData to Waiting in the Azure data factory WikiADF.

The UpdateType is set to UpstreamInPipeline, which means that status of each slice for the dataset and all the dependent (upstream) datasets which are used as input datasets for activities in the pipeline is set to Waiting.
Other possible value for this parameter is Individual.

## PARAMETERS

### -DataFactory
Specifies an object.
This cmdlet modifies the status of slices that belong to the data factory that this parameter specifies.

```yaml
Type: PSDataFactory
Parameter Sets: ByFactoryObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DataFactoryName
Specifies the name of the Azure data factory.

```yaml
Type: String
Parameter Sets: ByFactoryName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndDateTime
Specifies the end date-time for the slice.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group.

```yaml
Type: String
Parameter Sets: ByFactoryName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDateTime
Specifies the start date-time for the slice.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Specifies the status of the data slice.
These are the possible values for the status parameter and their descriptions:

Ready - Data processing has completed and the data slice is ready.

Waiting - Data processing has not started yet.

PendingValidation - Data slice is waiting for pending validation on whether it fulfills the against validation policies before being processed.

Skip  - Skip processing of the slice.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatasetName
Specifies the name of the dataset.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UpdateType
Type of update to the slice.
These are the possible values for the UpdateType parameter and their descriptions:

Individual - Sets the status of each slice for the dataset in the specified time range.

UpstreamInPipeline - Sets the status of each slice for the dataset and all the dependent (upstream) datasets which are used as input datasets for activities in the pipeline.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Azure Data Factory Cmdlets](.\AzureRM.DataFactories.md)

