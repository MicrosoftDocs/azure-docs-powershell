---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 7a828f4d-bcad-4c9a-8a41-ea9bedde2552
schema: 2.0.0
---

# Get-AzureDataFactoryRun

## SYNOPSIS
Get all the runs for a data slice of a dataset in an Azure data factory.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzureDataFactoryRun [-DataFactoryName] <String> [-DatasetName] <String> [-StartDateTime] <DateTime>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzureDataFactoryRun [-DataFactory] <PSDataFactory> [-DatasetName] <String> [-StartDateTime] <DateTime>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureDataFactoryRun** cmdlet gets all the runs for a data slice of a dataset in an Azure  data factory. 
A dataset in an Azure data factory is composed of slices over the time axis.
The width of a slice is determined by the schedule - hourly/daily.
The run is an unit of processing for a slice.
There could be one or more runs for a slice in case of retries or if you rerun your slice in case of failures.
A slice is identified by its start time.
Therefore for the Get-AzureDataFactoryRun cmdlet, you need to pass in the start time of the slice from the results of the Get-AzureDataFactorySlice cmdlet.

For example, to get a run for the following slice, you use 2015-04-02T20:00:00.

ResourceGroupName  : ADF

DataFactoryName : SPDataFactory0924

DatasetName : MarketingCampaignEffectivenessBlobTable

Start : 5/2/2014 8:00:00 PM

End : 5/3/2014 8:00:00 PM

RetryCount : 0

Status : Ready

LatencyStatus :

## EXAMPLES

### Example 1: Get all runs for data slices in a specified dataset
```
PS C:\> Get-AzureDataFactoryRun -DataFactoryName "WikiADF" -DatasetName "DAWikiAggregatedData" -ResourceGroupName "ADF" -StartDateTime 2014-05-21T16:00:00
```

Gets all runs for slices of the dataset DAWikiAggregatedData in the Azure data factory WikiADF starting from 4 PM GMT on 05/21/2014.

## PARAMETERS

### -DataFactory
Specifies an object.
This cmdlet gets runs for slices that belong to the data factory that this parameter specifies.

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
Specifies the name of the data factory.

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
Specifies the start date time of the data slice.

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

### System.Collections.Generic.List`1[[Microsoft.WindowsAzure.Commands.Utilities.PSDataSliceRun, Microsoft.WindowsAzure.Commands.Utilities, Version=0.8.2.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

## NOTES

## RELATED LINKS

[Azure Data Factory Cmdlets](.\AzureRM.DataFactories.md)

