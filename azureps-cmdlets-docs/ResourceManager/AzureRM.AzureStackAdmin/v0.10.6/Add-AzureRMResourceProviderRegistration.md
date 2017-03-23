---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureRMResourceProviderRegistration

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### MultipleExtensions (Default)
```
Add-AzureRMResourceProviderRegistration -Name <String> -Namespace <String> -ResourceGroup <String>
 -ArmLocation <String> -ResourceManagerType <ResourceManagerType> -DisplayName <String>
 -ProviderLocation <String> [-Extensions <String>] -ResourceTypes <String> [<CommonParameters>]
```

### SingleExtension
```
Add-AzureRMResourceProviderRegistration -Name <String> -Namespace <String> -ResourceGroup <String>
 -ArmLocation <String> -ResourceManagerType <ResourceManagerType> -DisplayName <String>
 -ProviderLocation <String> -ExtensionName <String> -ExtensionUri <Uri> -ResourceTypes <String>
 [<CommonParameters>]
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

### -ArmLocation
{{Fill ArmLocation Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
{{Fill DisplayName Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionName
{{Fill ExtensionName Description}}

```yaml
Type: String
Parameter Sets: SingleExtension
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Extensions
{{Fill Extensions Description}}

```yaml
Type: String
Parameter Sets: MultipleExtensions
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionUri
{{Fill ExtensionUri Description}}

```yaml
Type: Uri
Parameter Sets: SingleExtension
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
{{Fill Name Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
{{Fill Namespace Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderLocation
{{Fill ProviderLocation Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroup
{{Fill ResourceGroup Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceManagerType
{{Fill ResourceManagerType Description}}

```yaml
Type: ResourceManagerType
Parameter Sets: (All)
Aliases: 
Accepted values: Default, Admin

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceTypes
{{Fill ResourceTypes Description}}

```yaml
Type: String
Parameter Sets: (All)
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

### None

## OUTPUTS

### Microsoft.AzureStack.Management.Models.ProviderRegistrationModel

## NOTES

## RELATED LINKS

