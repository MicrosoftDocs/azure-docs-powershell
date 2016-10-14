---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureDataFactory

## SYNOPSIS
Creates an Azure data factory.

## SYNTAX

```
New-AzureDataFactory [-Name] <String> [-Location] <String> [[-Tags] <Hashtable>] [-Force]
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
Creates an Azure data factory given the resource group name and location.
Only 'WestUS' is supported for location at this moment.
If the data factory with the same name already exists, you will need to confirm whether to overwrite the existing data factory unless you use the -force flag.

Here is the sequence of operations you perform:

1) Create a data factory.

2) Create linked services.

3) Create datasets

4) Create a pipeline.

See Data Factory - Naming Ruleshttps://msdn.microsoft.com/library/azure/dn835027.aspx topic on MSDN Library for naming rules for Data Factory artifacts.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> New-AzureDataFactory -Name WikiADF -ResourceGroupName ADF -Location WestUS
```

Creates an Azure data factory 'WikiADF' in the resource group 'ADF' in the 'WestUS' location.

## PARAMETERS

### -Force
Indicates that this cmdlet replaces an existing data factory without prompting you for confirmation.

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

### -Location
Location for the Azure data factory.
For example: westus or eastus.
Only westus is supported at this moment.

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

### -Name
Name of the data factory to be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the resource group to which the data factory should belong.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tags
Tags for the data factory.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

### Microsoft.WindowsAzure.Commands.Utilities.PSDataFactory

## NOTES

## RELATED LINKS

