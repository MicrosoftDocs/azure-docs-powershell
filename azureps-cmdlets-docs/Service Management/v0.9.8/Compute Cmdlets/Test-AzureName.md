---
external help file: SMAzure_Compute.xml
online version: 0c2a5092-db45-4ce7-b39b-d1e499b4a867
schema: 2.0.0
---

# Test-AzureName
## SYNOPSIS
Tests whether a Microsoft Azure cloud service name, storage service name or service bus namespace name exists or not.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Test-AzureName [-Service] [-Name] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Test-AzureName [-Storage] [-Name] <String>
```

### UNNAMED_PARAMETER_SET_3
```
Test-AzureName [-ServiceBusNamespace] [-Name] <String>
```

### UNNAMED_PARAMETER_SET_4
```
Test-AzureName [-Website] [-Name] <String>
```

## DESCRIPTION
If the name exists, the cmdlet returns $True.
If the name does not exist, it returns $False.

## EXAMPLES

### --------------  Example 1 --------------
```
C:\PS>Test-AzureName â€"Service "MyNameService1"
```

This command tests to see if the "MyNameService1" is an existing Microsoft Azure cloud service name.

### --------------  Example 2 --------------
```
C:\PS>Test-AzureName â€"Storage "mystorename1"
```

This command tests to see if the "mystorename1" is an existing Microsoft Azure storage service name.

### --------------  Example 3 --------------
```
C:\PS>Test-AzureName â€"ServiceBusNamespace "mynamespace"
```

This command tests to see if the "mynamespace" is an existing Microsoft Azure service bus namespace name.

## PARAMETERS

### -Name
Specifies the name of the service or storage account to test.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Service
Specifies to test for an existing service account.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceBusNamespace
Specifies to test for an existing service bus namespace.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storage
Specifies to test for an existing storage account.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Website
Specifies to test for an existing website.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
node-dev, php-dev, python-dev

## RELATED LINKS

