---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: .\Get-AzureDataFactoryDataset.md
schema: 2.0.0
---

# Remove-AzureDataFactoryDataset

## SYNOPSIS
Removes the specified dataset from an Azure data factory

## SYNTAX

### ByFactoryName (Default)
```
Remove-AzureDataFactoryDataset [-Force] [-DataFactoryName] <String> [-Name] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
Remove-AzureDataFactoryDataset [-Force] [-DataFactory] <PSDataFactory> [-Name] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureDataFactoryDataset** cmdlet removes the specified dataset from an Azure data factory.

## EXAMPLES

### Example 1: Remove a dataset from a data factory
```
PS C:\>Remove-AzureDataFactoryDataset "DAWikiAggregatedData" -DataFactoryName "WikiADF" -ResourceGroupName "RG001"
```

This command removes the dataset DAWikiAggregatedData from the Azure data factory WikiADF.

## PARAMETERS

### -DataFactory
Specifies a Data Factory object.
This cmdlet removes a dataset from the data factory that this parameter specifies.

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

### -Name
Specifies the name of the dataset.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DatasetName

Required: True
Position: 3
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

[Get-AzureDataFactoryDataset](.\Get-AzureDataFactoryDataset.md)

[New-AzureDataFactoryDataset](.\New-AzureDataFactoryDataset.md)

