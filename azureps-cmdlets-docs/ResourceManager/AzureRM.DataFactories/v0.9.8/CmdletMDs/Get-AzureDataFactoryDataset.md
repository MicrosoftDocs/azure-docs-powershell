---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: .\New-AzureDataFactoryDataset.md
schema: 2.0.0
---

# Get-AzureDataFactoryDataset

## SYNOPSIS
Gets information about a specific dataset or all datasets in an Azure data factory.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzureDataFactoryDataset [-DataFactoryName] <String> [[-Name] <String>] [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzureDataFactoryDataset [-DataFactory] <PSDataFactory> [[-Name] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureDataFactoryDataset** cmdlet gets information about a specific dataset or all datasets in an Azure data factory.
If you do not specify the name of a dataset, the cmdlet returns properties of all datasets in the Azure data factory.

## EXAMPLES

### Example 1: Get information about all datasets in a data factory
```
PS C:\>Get-AzureDataFactoryDataset -ResourceGroupName ADF -DataFactoryName "WikiADF"
```

This command gets information about all datasets in the Azure data factory WikiADF.

### Example 2: Get information about a specific dataset in a data factory
```
PS C:\>Get-AzureDataFactoryDataset -ResourceGroupName ADF -DataFactoryName "WikiADF" -Name "DAWikipediaClickEvents"
```

This command gets information about the dataset DAWikipediaClickEvents in the Azure data factory WikiADF.

### Example 3: Get location details for a specific dataset
```
PS C:\>(Get-AzureDataFactoryDataset -ResourceGroupName "ADF" -DataFactoryName "WikiADF" -Name "DAWikipediaClickEvents").Location
```

This command gets location details for the dataset DAWikipediaClickEvents.
You can also assign the output of the Get-AzureDataFactoryDataset cmdlet to a variable and then print Location property of the output variable.

## PARAMETERS

### -DataFactory
Specifies a Data Factory object.
This cmdlet gets datasets that belong to the data factory that this parameter specifies.

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

### -Name
Specifies the name of the dataset.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the Azure resource group.

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

## NOTES

## RELATED LINKS

[New-AzureDataFactoryDataset](.\New-AzureDataFactoryDataset.md)

[Remove-AzureDataFactoryDataset](.\Remove-AzureDataFactoryDataset.md)

