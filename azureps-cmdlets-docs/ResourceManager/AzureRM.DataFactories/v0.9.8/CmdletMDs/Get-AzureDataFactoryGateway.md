---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 474a5345-83d2-40a4-b12f-83ed8b5db410
schema: 2.0.0
---

# Get-AzureDataFactoryGateway

## SYNOPSIS
Gets information about a specific gateway or all gateways in an Azure data factory.

## SYNTAX

### ByFactoryName (Default)
```
Get-AzureDataFactoryGateway [-DataFactoryName] <String> [[-Name] <String>] [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
Get-AzureDataFactoryGateway [-DataFactory] <PSDataFactory> [[-Name] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureDataFactoryGateway cmdlet gets information about a specific gateway or all gateways in an Azure data factory.
You need to install a gateway on your on-premises computer so to be able add an on-premises SQL Server as a linked service to a data factory.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Get-AzureDataFactoryGateway -ResourceGroupName ADF -DataFactoryName wikiadf
```

Gets information about all gateways in the Azure data factory 'WikiADF'.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Get-AzureDataFactoryGateway -ResourceGroupName ADF -DataFactoryName wikiadf -Name gateway1
```

Gets information about the gateway 'gateway1' in the Azure data factory 'WikiADF'.

## PARAMETERS

### -DataFactory
Specifies a  object.
This cmdlet gets information about logical gateways in the data factory that this parameter specifies.

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

### -Name
Name of the gateway.

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

### System.Collections.Generic.List`1[[Microsoft.WindowsAzure.Commands.Utilities.PSDataFactoryGateway]], Microsoft.WindowsAzure.Commands.Utilities.PSDataFactoryGateway

## NOTES

## RELATED LINKS

