---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: aa2455de-930d-474f-81a3-c818e74666b5
schema: 2.0.0
---

# Get-AzureDataFactory

## SYNOPSIS
Gets information about a specific Azure data factory or all Azure data factories in the specified Azure resource group.

## SYNTAX

```
Get-AzureDataFactory [[-Name] <String>] [-ResourceGroupName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureDataFactory cmdlet gets information about a specific Azure data factory or all Azure data factories in the specified Azure resource group.
If the data factory name is not specified, all the Azure data factories in the subscription are returned.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Get-AzureDataFactory -ResourceGroupName ADF
```

Displays information about all data factories in the Azure subscription.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Get-AzureDataFactory -ResourceGroupName ADF -Name WikiADF
```

Displays information about the data factory 'WikiADF' in the Azure subscription.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\> Get-AzureDataFactory WikiADF -ResourceGroupName
```

Displays information about the data factory 'WikiADF' in the Azure subscription.
This example is same as the previous one except that the "-Name" is not used in the command.

## PARAMETERS

### -Name
Name of the data factory.

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
Parameter Sets: (All)
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

### System.Collections.Generic.List`1[[Microsoft.WindowsAzure.Commands.Utilities.PSDataFactory, Microsoft.WindowsAzure.Commands.Utilities, Version=0.8.2.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]] Microsoft.WindowsAzure.Commands.Utilities.PSDataFactory

## NOTES

## RELATED LINKS

