---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 4076bd7c-248e-4f9f-b93a-7f2ffb9b0a51
schema: 2.0.0
---

# New-AzureDataFactoryGatewayKey

## SYNOPSIS
Creates a gateway key for the specified Azure data factory gateway.

## SYNTAX

### ByFactoryName (Default)
```
New-AzureDataFactoryGatewayKey [-DataFactoryName] <String> [-GatewayName] <String>
 [-ResourceGroupName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
New-AzureDataFactoryGatewayKey [-DataFactory] <PSDataFactory> [-GatewayName] <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The New-AzureDataFactoryGatewayKey cmdlet creates a gateway key for the specified Azure data factory gateway.
You register the gateway with cloud service using this key.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> New-AzureDataFactoryGatewayKey -ResourceGroupName ADF -GatewayName gatewaySample -DataFactoryName wikiADF | Format-List
```

Creates a gateway key for the Azure data factory gateway 'gatewaySample'.

## PARAMETERS

### -DataFactory
Specifies a  object.
This cmdlet creates a gateway key for the data factory that this parameter specifies.

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

### -GatewayName
Name of the gateway.

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

### Microsoft.WindowsAzure.Commands.Utilities.PSDataFactoryGatewayKey

## NOTES

## RELATED LINKS

