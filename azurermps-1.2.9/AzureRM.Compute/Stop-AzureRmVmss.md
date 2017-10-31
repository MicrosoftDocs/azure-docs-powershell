---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: 
schema: 2.0.0
---

# Stop-AzureRmVmss

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### InvokeByDynamicParameters (Default)
```
Stop-AzureRmVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String> [[-InstanceId] <String[]>]
 [<CommonParameters>]
```

### InvokeByDynamicParametersForFriendMethod
```
Stop-AzureRmVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String> [[-InstanceId] <String[]>]
 [-StayProvisioned] [<CommonParameters>]
```

### InvokeByStaticParametersForFriendMethod
```
Stop-AzureRmVmss [-StayProvisioned] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -InstanceId
{{Fill InstanceId Description}}

```yaml
Type: String[]
Parameter Sets: InvokeByDynamicParameters, InvokeByDynamicParametersForFriendMethod
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
{{Fill ResourceGroupName Description}}

```yaml
Type: String
Parameter Sets: InvokeByDynamicParameters, InvokeByDynamicParametersForFriendMethod
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StayProvisioned
{{Fill StayProvisioned Description}}

```yaml
Type: SwitchParameter
Parameter Sets: InvokeByDynamicParametersForFriendMethod, InvokeByStaticParametersForFriendMethod
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMScaleSetName
{{Fill VMScaleSetName Description}}

```yaml
Type: String
Parameter Sets: InvokeByDynamicParameters, InvokeByDynamicParametersForFriendMethod
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

