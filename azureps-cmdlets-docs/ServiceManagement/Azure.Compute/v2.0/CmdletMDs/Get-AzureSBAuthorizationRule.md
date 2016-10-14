---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: .\New-AzureSBAuthorizationRule.md
schema: 2.0.0
---

# Get-AzureSBAuthorizationRule

## SYNOPSIS
Gets Service bus authorization rules

## SYNTAX

### NamespaceSAS
```
Get-AzureSBAuthorizationRule [-Name <String>] [-Permission <AccessRights[]>] -Namespace <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### EntitySAS
```
Get-AzureSBAuthorizationRule [-Name <String>] [-Permission <AccessRights[]>] -Namespace <String>
 -EntityName <String> -EntityType <ServiceBusEntityType> [-Profile <AzureSMProfile>] [<CommonParameters>]
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

### -Name
The unique authorization rule name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EntityName
The entity name to apply rule at.

```yaml
Type: String
Parameter Sets: EntitySAS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EntityType
The entity type (Queue, Topic, Relay, NotificationHub).

```yaml
Type: ServiceBusEntityType
Parameter Sets: EntitySAS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permission
The authorization permissions to filter (Send, Manage, Listen).
This uses exact match

```yaml
Type: AccessRights[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
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

## NOTES

## RELATED LINKS

[New-AzureSBAuthorizationRule](.\New-AzureSBAuthorizationRule.md)

[Remove-AzureSBAuthorizationRule](.\Remove-AzureSBAuthorizationRule.md)

[Set-AzureSBAuthorizationRule](.\Set-AzureSBAuthorizationRule.md)

