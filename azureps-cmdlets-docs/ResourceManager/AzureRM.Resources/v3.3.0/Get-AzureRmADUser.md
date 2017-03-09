---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: BF254F2F-F658-45CC-8AC8-53FF96CFCAAD
online version: 
schema: 2.0.0
---

# Get-AzureRmADUser

## SYNOPSIS
Gets active directory users.

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzureRmADUser [-UserPrincipalName <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### SearchStringParameterSet
```
Get-AzureRmADUser -SearchString <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### ObjectIdParameterSet
```
Get-AzureRmADUser -ObjectId <Guid> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### UPNParameterSet
```
Get-AzureRmADUser -UserPrincipalName <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### MailParameterSet
```
Get-AzureRmADUser -Mail <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The **Get-AzureRmADUser** cmdlet gets active directory users.

## EXAMPLES

### Example 1: Get a user using UPN
```
PS C:\> Get-AzureRmADUser -UPN "pattifuller@contoso.com"
```

This command gets the user named pattifuller@contoso.com

### Example 2: Get users using a search string
```
PS C:\> Get-AzureRmADUser -SearchString "contoso"
```

This command gets all Active Directory users that has contoso in the display name.

### Example 3: Get all Active Directory users
```
PS C:\> Get-AzureRmADUser
```

This command gets all Active Directory users.

## PARAMETERS

### -UserPrincipalName
Specifies the user principal name (UPN) of the user that this cmdlet gets.

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

### -SearchString
Specifies the name of the user display.

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
Specifies the object ID of the user.

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
Specifies the email of the user.

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

[New-AzureRmADUser](./New-AzureRmADUser.md)

[Set-AzureRmADUser](./Set-AzureRmADUser.md)

[Remove-AzureRmADUser](./Remove-AzureRmADUser.md)
