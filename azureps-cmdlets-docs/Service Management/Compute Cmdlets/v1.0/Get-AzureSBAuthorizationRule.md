---
external help file: SMAzure_Compute.xml
online version: 3e60e1c8-7421-4762-befc-5c8974f684c4
schema: 2.0.0
---

# Get-AzureSBAuthorizationRule
## SYNOPSIS
Gets Service bus authorization rules

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureSBAuthorizationRule [[-Name] <String>] [-Permission] [-Namespace] <String> [-EntityName] <String>
 [-EntityType] <ServiceBusEntityType>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureSBAuthorizationRule [[-Name] <String>] [-Permission] [-Namespace] <String>
```

## DESCRIPTION
Gets Service bus authorization rules

## EXAMPLES

### -------------- Get authorization rule at namespace level --------------
```
C:\PS>Get-AzureSBAuthorizationRule -Namespace MyNamespace
```

Gets all available authorization rules at MyNamespace

### -------------- Get authorization rule for a Queue --------------
```
C:\PS>Get-AzureSBAuthorizationRule -Namespace MyNamespace -EntityName MyEntity -EntityType Queue
```

Gets all available authorization rules a MyEntity Queue on MyNamespace

### -------------- Get authorization rule by name --------------
```
C:\PS>Get-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace
```

Gets an authorization rule called MyRule on MyNamespace level

### -------------- Get authorization rule by permisssion --------------
```
C:\PS>Get-AzureSBAuthorizationRule -Namespace MyNamespace -Permission $("Send")
```

Gets all authorization rules that have send permission on namespace level

## PARAMETERS

### -EntityName
The entity name to apply rule at.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 4
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
Position: 5
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

Required: False
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
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permission
The authorization permissions to filter (Send, Manage, Listen).
This uses exact match

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Manage, Send, Listen

Required: False
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureSBAuthorizationRule](3e60e1c8-7421-4762-befc-5c8974f684c4)

[Remove-AzureSBAuthorizationRule](7d4951b1-15ff-4fa4-9122-36538eee9cbe)

[Set-AzureSBAuthorizationRule](c199f0d5-8f84-4106-ac4b-afc2192d1218)

