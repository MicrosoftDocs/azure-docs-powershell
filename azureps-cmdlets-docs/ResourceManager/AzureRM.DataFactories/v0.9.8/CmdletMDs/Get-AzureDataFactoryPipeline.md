---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureDataFactoryPipeline

## SYNOPSIS
Gets information about a specific pipeline or all pipelines in an Azure data factory.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzureDataFactoryPipeline [[-Name] <String>] [-DataFactoryName] <String> [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzureDataFactoryPipeline [[-Name] <String>] [-DataFactory] <PSDataFactory> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureDataFactoryPipeline cmdlet gets information about a specific pipeline or all pipelines in an Azure data factory.
If you specify a pipeline name for the Name parameter, it returns information about that specific pipeline; otherwise, it returns information about all the pipelines.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Get-AzureDataFactoryPipeline -ResourceGroupName ADF -DataFactoryName wikiadf
```

Gets information about all pipelines in the Azure data factory 'WikiADF'.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Get-AzureDataFactoryPipeline -ResourceGroupName ADF -DataFactoryName wikiadf -Name DPWikisample | format-list
```

Gets information about the pipeline 'DPWikisample' in the Azure data factory 'WikiADF'.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\> (Get-AzureDataFactoryPipeline -ResourceGroupName ADF -DataFactoryName WikiADF -Name DPWikisample).Properties
```

Prints properties of the pipeline 'DPWikisample' in the Azure data factory 'WikiADF'.

### -------------------------- EXAMPLE 4 --------------------------
```
PS C:\> (Get-AzureDataFactoryPipeline -ResourceGroupName ADF -DataFactoryName WikiADF -Name DPWikisample).Properties.Activities
```

Displays information about all the activities in the pipeline 'DPWikisample'.

### -------------------------- EXAMPLE 5 --------------------------
```
PS C:\> (Get-AzureDataFactoryPipeline -ResourceGroupName ADF -DataFactoryName WikiADF -Name DPWikisample).Properties.RuntimeInfo
```

Returns the runtime information for the pipeline 'DPWikiSample'.

### -------------------------- EXAMPLE 6 --------------------------
```
PS C:\> (Get-AzureDataFactoryPipeline -ResourceGroupName ADF -DataFactoryName WikiADF11 -Name DPWikisample).Properties.Activities[0].Inputs | format-list
```

Displays information about inputs for the first activity (Copy Activity) in the pipeline 'DPWikisample'.

## PARAMETERS

### -DataFactory
Specifies a  object.
This cmdlet gets pipelines that belong to the data factory that this parameter specifies.

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
Name of the Azure data factory.

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

### -Name
Name of the pipeline.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the resource group.

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

### -Profile
@{Text=}

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

### System.Collections.Generic.List`1[[Microsoft.WindowsAzure.Commands.Utilities.PSPipeline, Microsoft.WindowsAzure.Commands.Utilities, Version=0.8.2.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]] Microsoft.WindowsAzure.Commands.Utilities.PSPipeline

## NOTES

## RELATED LINKS

