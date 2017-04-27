---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmADUser

## SYNOPSIS
Filters active directory users.

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzureRmADUser [-UserPrincipalName <String>]
```

### SearchStringParameterSet
```
Get-AzureRmADUser -SearchString <String>
```

### ObjectIdParameterSet
```
Get-AzureRmADUser -ObjectId <Guid>
```

### UPNParameterSet
```
Get-AzureRmADUser -UserPrincipalName <String>
```

### MailParameterSet
```
Get-AzureRmADUser -Mail <String>
```

## DESCRIPTION
Filters active directory users.

## EXAMPLES

### --------------------------  Filters users using UPN  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Get-AzureRmADUser -UPN foo@domain.com
```

Gets user with foo@domain.com

### --------------------------  Filters users using Search String  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Get-AzureRmADUser -SearchString Joe
```

Filters all ad users that has Joe in the display name.

### --------------------------  List AD users  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Get-AzureRmADUser
```

Gets all AD users

## PARAMETERS

### -UserPrincipalName
UPN of the user.

```yaml
Type: String
Parameter Sets: EmptyParameterSet
Aliases: UPN

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UPNParameterSet
Aliases: UPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SearchString
The user display name

```yaml
Type: String
Parameter Sets: SearchStringParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Object id of the user.

```yaml
Type: Guid
Parameter Sets: ObjectIdParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Mail
@{Text=}

```yaml
Type: String
Parameter Sets: MailParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmADGroup]()

[Get-AzureRmADServicePrincipal]()

[Get-AzureRmADGroupMember]()

