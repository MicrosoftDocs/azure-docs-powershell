---
external help file: SMAzure_Compute.xml
online version: 07ab8d50-c6de-45f1-8576-99b76f798bca
schema: 2.0.0
---

# Remove-AzureSBAuthorizationRule
## SYNOPSIS
Removes existing Service Bus authorization rule

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-AzureSBAuthorizationRule [-Name] <String> [-Namespace] <String> [-EntityName] <String>
 [-EntityType] <ServiceBusEntityType> [-PassThru]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-AzureSBAuthorizationRule [-Name] <String> [-Namespace] <String> [-PassThru]
```

## DESCRIPTION
Removes existing Service Bus authorization rule

## EXAMPLES

### -------------- Remove authorization rule at namespace level --------------
```
C:\PS>Remove-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace
```

Removes authorization rule MyRule from MyNamespace

### -------------- Remove authorization rule for a Queue --------------
```
C:\PS>Remove-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace -EntityName MyEntity -EntityType Queue
```

Removes authorization rule called MyRule for a MyEntity Queue on MyNamespace

## PARAMETERS

### -EntityName
The entity name to apply rule at.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EntityType
The entity type (Queue, Topic, Relay, NotificationHub).

```yaml
Type: ServiceBusEntityType
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 4
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The unique authorization rule name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
The namespace name to apply the authorization rule.
If no EntityName provided the rule will be on the namespace level

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

### -PassThru
Indicates that this cmdlet returns an object representing the item on which it operates.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSBAuthorizationRule](07ab8d50-c6de-45f1-8576-99b76f798bca)

[New-AzureSBAuthorizationRule](3e60e1c8-7421-4762-befc-5c8974f684c4)

[Set-AzureSBAuthorizationRule](c199f0d5-8f84-4106-ac4b-afc2192d1218)

