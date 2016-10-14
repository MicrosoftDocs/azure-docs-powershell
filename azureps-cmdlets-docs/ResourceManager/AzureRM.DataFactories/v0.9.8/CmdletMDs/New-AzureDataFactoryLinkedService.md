---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureDataFactoryLinkedService

## SYNOPSIS
Links a data store or a compute service to the specified Azure data factory.

## SYNTAX

### ByFactoryName (Default)
```
New-AzureDataFactoryLinkedService [-DataFactoryName] <String> [[-Name] <String>] [-File] <String> [-Force]
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
New-AzureDataFactoryLinkedService [-DataFactory] <PSDataFactory> [[-Name] <String>] [-File] <String> [-Force]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureDataFactoryLinkedService** cmdlet links a data store or a compute service to the data factory.
You need to create linked services before creating datasets in an Azuredata factory.
If a linked service with the same name already exists, you will need to confirm whether to overwrite the existing linked service unless you specify the -force flag.

Here is the sequence of operations you perform:

1) Create a data factory.

2) Create linked services.

3) Create datasets

4) Create a pipeline

See Data Factory - Naming Ruleshttps://msdn.microsoft.com/library/azure/dn835027.aspx topic on MSDN Library for naming rules for Data Factory artifacts.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> New-AzureDataFactoryLinkedService -ResourceGroupName ADF -Name LinkedServiceCuratedWikiData -DataFactoryName wikiadf -File c:\\samples\\WikiSample\\LinkedServiceCuratedWikiData.json | format-list
```

Creates a linked service 'LinkedServiceCuratedWikiData' in the Azure data factory 'WikiADF'.
This linked service links an Azure blob store specified in the JSON file to the Azure data factory 'WikiADF'.

## PARAMETERS

### -DataFactory
Specifies an object.
This cmdlet creates a linked service for the data factory that this parameter specifies.

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

### -File
Specifies the file path including the name of the JSON file that has the description of the linked service.

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

### -Force
Indicates that this cmdlet replaces an existing linked service without prompting you for confirmation.

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
Specifies the name of the linked service.

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

### Microsoft.WindowsAzure.Commands.Utilities.PSLinkedService

## NOTES

## RELATED LINKS

