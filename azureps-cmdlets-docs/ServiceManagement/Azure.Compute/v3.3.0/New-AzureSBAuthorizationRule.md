---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 75320133-E7B1-40D4-B16D-567686D5AE99
online version: 
schema: 2.0.0
---

# New-AzureSBAuthorizationRule

## SYNOPSIS
Creates new Service Bus authorization rule.

## SYNTAX

### EntitySAS
```
New-AzureSBAuthorizationRule [-Name] <String> [[-Permission] <AccessRights[]>] [-Namespace] <String>
 [-EntityName] <String> [-EntityType] <ServiceBusEntityType> [[-PrimaryKey] <String>]
 [[-SecondaryKey] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### NamespaceSAS
```
New-AzureSBAuthorizationRule [-Name] <String> [[-Permission] <AccessRights[]>] [-Namespace] <String>
 [[-PrimaryKey] <String>] [[-SecondaryKey] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSBAuthorizationRule** cmdlet creates a Service Bus authorization rule.

## EXAMPLES

### Example 1: Create an authorization rule with generated primary key
```
PS C:\> New-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace -Permission $("Send")
```

Creates new authorization rule on namespace level with Send permission.

### Example 2: Creates an authorization rule by providing the primary key
```
PS C:\> New-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace -Permission $("Manage", "Listen", "Send") -EntityName MyEntity -EntityType Queue -PrimaryKey P+lL/Mnd2Z9sj5hwMrRyAxQDdX8RHfbdqU2eIAqs1rc=
```

Creates new authorization rule on MyEntity Queue level with all permissions.

## PARAMETERS

### -EntityName
Specifies the entity name to apply rule at.

```yaml
Type: String
Parameter Sets: EntitySAS
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntityType
Specifies the entity type.
Valid values are:
  
- Queue
- Topic
- Relay
- NotificationHub

```yaml
Type: ServiceBusEntityType
Parameter Sets: EntitySAS
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the unique authorization rule name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
Specifies the namespace name to apply the authorization rule.
If no *EntityName* provided the rule will be on the namespace level.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Permission
The authorization permissions (Send, Manage, Listen).

```yaml
Type: AccessRights[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryKey
Specifies the Shared Access Signature primary key.
Will be generated if not provided.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryKey
Specifies the Shared Access Signature secondary key.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
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

[Get-AzureSBAuthorizationRule](./Get-AzureSBAuthorizationRule.md)

[Remove-AzureSBAuthorizationRule](./Remove-AzureSBAuthorizationRule.md)

[Set-AzureSBAuthorizationRule](./Set-AzureSBAuthorizationRule.md)


