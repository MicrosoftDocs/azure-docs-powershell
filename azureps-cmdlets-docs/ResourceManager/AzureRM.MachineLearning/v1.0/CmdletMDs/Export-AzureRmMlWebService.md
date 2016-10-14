---
external help file: Microsoft.Azure.Commands.MachineLearning.dll-Help.xml
online version: .\Get-AzureRmMlWebService.md
schema: 2.0.0
---

# Export-AzureRmMlWebService

## SYNOPSIS
Exports a web service definition object as JSON.

## SYNTAX

### Export to file.
```
Export-AzureRmMlWebService -WebService <WebService> -OutputFile <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Export to JSON string.
```
Export-AzureRmMlWebService -WebService <WebService> [-ToJsonString] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-AzureRmMlWebService** cmdlet exports the given web service definition object to a JavaScript Object Notation (JSON) string that can be returned immediately or saved to a file.

## EXAMPLES

### Example 1: Export a web service definition as a string
```
PS C:\>Export-AzureRmMlWebService -WebService $SVC -ToJsonString
```

This command exports a web service definition as a string.

### Example 2: Export a web service definition to a file
```
PS C:\>Export-AzureRmMlWebService -WebService $SVC -OutputFile "C:\mlservice.json"
```

This command exports a web service definition to a file named C:\mlservice.json.

## PARAMETERS

### -WebService
Specifies the web service definition object to be exported.

```yaml
Type: WebService
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OutputFile
Specifies the file path to export the definition to.

```yaml
Type: String
Parameter Sets: Export to file.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToJsonString
Indicates that the cmdlet exports the definition as a JSON string.

```yaml
Type: SwitchParameter
Parameter Sets: Export to JSON string.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
ps_force

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

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* Keywords: azure, azurerm, arm, resource, management, manager, machine, machine learning, azureml

## RELATED LINKS

[Get-AzureRmMlWebService](.\Get-AzureRmMlWebService.md)

[Import-AzureRmMlWebService](.\Import-AzureRmMlWebService.md)

[New-AzureRmMlWebService](.\New-AzureRmMlWebService.md)

[Remove-AzureRmMlWebService](.\Remove-AzureRmMlWebService.md)

[Update-AzureRmMlWebService](.\Update-AzureRmMlWebService.md)

