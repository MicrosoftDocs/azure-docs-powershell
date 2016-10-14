---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureDataFactoryPipelineActivePeriod

## SYNOPSIS
Sets the active period for the data slices that are processed by the pipeline.

## SYNTAX

### ByFactoryName (Default)
```
Set-AzureDataFactoryPipelineActivePeriod [-PipelineName] <String> [-DataFactoryName] <String>
 [-StartDateTime] <DateTime> [[-EndDateTime] <DateTime>] [-AutoResolve] [-ForceRecalculate] [-Force]
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
Set-AzureDataFactoryPipelineActivePeriod [-PipelineName] <String> [-DataFactory] <PSDataFactory>
 [-StartDateTime] <DateTime> [[-EndDateTime] <DateTime>] [-AutoResolve] [-ForceRecalculate] [-Force]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureDataFactoryPipelineActivePeriod** cmdlet Sets the active period for the data slices that are processed by the pipeline.
If you use Set-AzureDataFactorySliceStatus, make sure that the slice startdate and end date are in the active period of the pipeline.
Once the pipelines are created, you can specify the duration in which data processing will occur.
By specifying the active period for a pipeline, you are defining the time duration in which the data slices will be processed based on the Availability properties that were defined for each Azure Data Factory dataset.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Set-AzureDataFactoryPipelineActivePeriod  -Name DPWikisample -ResourceGroupName ADF -DataFactoryName WikiADF -StartDateTime 2014-05-21T16:00:00 -EndDateTime 2014-05-22T16:00:00
```

Sets the active period for the data slices that are processed by the pipeline 'DPWikisample' to 5/21/2014 4 PM GMT to 5/22/2014 4 PM GMT.

## PARAMETERS

### -AutoResolve
Auto resolve active periods of conflicting pipelines.

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

### -DataFactory
Specifies a  object.
This cmdlet modifies the active period for a pipeline that belongs to the data factory that this parameter specifies.

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
Name of the data factory.

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
The end date-time of the duration in which data processing will occur or the data slices will be processed.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -ForceRecalculate
Indicates that this cmdlet marks all data slices in the period as Waiting to force re-calculation.

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

### -PipelineName
Specifies the name of the pipeline.
This cmdlet sets the active period for the pipeline that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

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
Specifies the start date-time of the duration in which data processing will occur or the data slices will be processed.

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

