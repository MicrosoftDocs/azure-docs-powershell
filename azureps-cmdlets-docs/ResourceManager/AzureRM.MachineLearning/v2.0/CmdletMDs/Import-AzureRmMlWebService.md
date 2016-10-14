---
external help file: Microsoft.Azure.Commands.MachineLearning.dll-Help.xml
online version: .\Export-AzureRmMlWebService.md
schema: 2.0.0
---

# Import-AzureRmMlWebService

## SYNOPSIS
Imports a web service definition to an object instance.

## SYNTAX

### Import from JSON file.
```
Import-AzureRmMlWebService -InputFile <String> [<CommonParameters>]
```

### Import from JSON string.
```
Import-AzureRmMlWebService -JsonString <String> [<CommonParameters>]
```

## DESCRIPTION
The **Import-AzureRmMlWebService** cmdlet imports a web service definition instance from a JavaScript Object Notation (JSON) object specified either directly or in a referenced file.

## EXAMPLES

### Example 1: Import a web service definition from string
```
PS C:\>Import-AzureRmMlWebService -JsonString $JSONDefinition
```

This command imports a web service definition from a string defined in the variable named $JSONDefinition.

### Example 2: Import a web service definition from a file path
```
PS C:\>Import-AzureRmMlWebService -InputFile "C:\mlservice.json"
```

This command imports a web service definition from the input file named C:\mlservice.json.

## PARAMETERS

### -InputFile
Specifies the JSON file path from where the cmdlet imports the web service definition.

```yaml
Type: String
Parameter Sets: Import from JSON file.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
Specifies the JSON formatted string that contains the web service definition that this cmdlet imports.

```yaml
Type: String
Parameter Sets: Import from JSON string.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## NOTES
* Keywords: azure, azurerm, arm, resource, management, manager, machine, machine learning, azureml

## RELATED LINKS

[Export-AzureRmMlWebService](.\Export-AzureRmMlWebService.md)

[Get-AzureRmMlWebService](.\Get-AzureRmMlWebService.md)

[New-AzureRmMlWebService](.\New-AzureRmMlWebService.md)

[Remove-AzureRmMlWebService](.\Remove-AzureRmMlWebService.md)

[Update-AzureRmMlWebService](.\Update-AzureRmMlWebService.md)

