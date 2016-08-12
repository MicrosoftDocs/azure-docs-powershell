---
external help file: SMAzure_Compute.xml
online version: 07ab8d50-c6de-45f1-8576-99b76f798bca
schema: 2.0.0
---

# Set-AzureSBAuthorizationRule
## SYNOPSIS
Updates existing Service Bus authorization rule

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-AzureSBAuthorizationRule [-Name] <String> [-Permission] [-Namespace] <String> [-EntityName] <String>
 [-EntityType] <ServiceBusEntityType> [[-PrimaryKey] <String>] [[-SecondaryKey] <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-AzureSBAuthorizationRule [-Name] <String> [-Permission] [-Namespace] <String> [[-PrimaryKey] <String>]
 [[-SecondaryKey] <String>]
```

## DESCRIPTION
Updates existing Service Bus authorization rule

## EXAMPLES

### -------------- Renew primary key for authorization rule at namespace level --------------
```
C:\PS>Set-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace -Permission $("Send")
```

The primary key is renewed

### -------------- Update authorization rule permission --------------
```
C:\PS>Set-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace -Permission $("Listen", "Send") -EntityName MyEntity -EntityType Queue
```

Updates the permissions

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
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permission
The authorization permissions (Send, Manage, Listen)

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Manage, Send, Listen

Required: False
Position: 2
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryKey
The Shared Access Signature primary key.
Will be generated if not provided

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryKey
The Shared Access Signature secondary key

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
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

[Remove-AzureSBAuthorizationRule](7d4951b1-15ff-4fa4-9122-36538eee9cbe)

