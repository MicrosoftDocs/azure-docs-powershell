---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: .\Set-AzureDataFactorySliceStatus.md
schema: 2.0.0
---

# Get-AzureDataFactorySlice

## SYNOPSIS
Gets all the slices for a dataset in an Azure data factory that are produced after the specified time.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzureDataFactorySlice [[-EndDateTime] <DateTime>] [-DataFactoryName] <String> [-DatasetName] <String>
 [-StartDateTime] <DateTime> [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzureDataFactorySlice [[-EndDateTime] <DateTime>] [-DataFactory] <PSDataFactory> [-DatasetName] <String>
 [-StartDateTime] <DateTime> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureDataFactorySlice** cmdlet gets all the slices for a dataset in an Azure data factory that are produced after the StartDateTime and before the EndDateTime.
The data slice with status Ready is ready for consumption by dependent slices.

Status                                   Description

============               ========================================================

Waiting                 Data processing has not started yet.

InProgress                             Data processing is in-progress.

Ready                                    Data processing has completed and the data slice is ready.

Failed                                    Execution of the run that produces the slice failed

Skip                                       Skip processing of the slice.

Retry                                     Retrying the run that produces the slice

Timed Out                            Data processing has timed out.

PendingValidation               Data slice is waiting for validation against validation policies before being processed.

Retry Validation                   Retry the validation of the slice

Failed Validation                  Validation of the slice failed

For each of the slices, you can drill-down deeper, and see more information about the run that is producing the slice by using the Get-AzureDataFactoryRun cmdlets.

## EXAMPLES

### Example 1: Get all data slices for a specific dataset
```
PS C:\> Get-AzureDataFactorySlice -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -DatasetName "DAWikiAggregatedData" -StartDateTime 2014-05-20T10:00:00
```

Gets all the data slices for the dataset WikiAggregatedData in the Azure data factory WikiADF produced after 2014-05-20T10:00:00 (GMT).
The availability for this dataset is set to every hour in the JSON file as shown below:



    availability:

{

period: "Hour",

periodMultiplier: 1

}

Notice that some of the artifacts are in Ready state and others are in the Waiting state.
The ones in Ready state have already been executed and others are waiting for execution at the end of each hour in the interval specified by using the Set-AzureDataFactoryPipelineActivePeriod.
In this example, both start and end periods for pipeline and slice are set to 1 day (24 hrs).

## PARAMETERS

### -DataFactory
Specifies an object.
This cmdlet gets slices that belong to the data factory that this parameter specifies.

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

### -EndDateTime
Specifies the data slices that are produced before the specified time are returned.

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
Specifies that the data slices that are produced after the specified time are returned.

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
@{Text=}

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

### System.Collections.Generic.List`1[[Microsoft.WindowsAzure.Commands.Utilities.PSDataSlice, Microsoft.WindowsAzure.Commands.Utilities, Version=0.8.2.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

## NOTES

## RELATED LINKS

[Set-AzureDataFactorySliceStatus](.\Set-AzureDataFactorySliceStatus.md)

[Azure Data Factory Cmdlets](.\AzureRM.DataFactories.md)

