---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: 85DDA491-7A7D-4217-B0E3-72CDC3787889
online version: 
schema: 2.0.0
---

# Get-AzureRmADGroup

## SYNOPSIS
Filters Active Directory groups.

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzureRmADGroup [-ObjectId <Guid>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### SearchStringParameterSet
```
Get-AzureRmADGroup -SearchString <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### ObjectIdParameterSet
```
Get-AzureRmADGroup -ObjectId <Guid> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The **Get-AzureRmADGroup** cmdlet filters Active Directory groups.

## EXAMPLES

### Example 1: Get an AD group by ID

```
PS C:\> Get-AzureRmADGroup -ObjectId 85F89C90-780E-4AA6-9F4F-6F268D322EEE
```

This command gets the group with the ID 85F89C90-780E-4AA6-9F4F-6F268D322EEE.

### Example 2: Get a group by search string

```
PS C:\> Get-AzureRmADGroup -SearchString "PattiFuller"
```

This command gets all AD groups that have PattiFuller in the display name.

### Example 3: Get all AD groups

```
PS C:\> Get-AzureRmADGroup
```

This command gets all AD groups.

## PARAMETERS

### -ObjectId
Specifies the object ID of the Active Directory Group.

```yaml
Type: Guid
Parameter Sets: EmptyParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Specifies the display name of the group.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmADUser](./Get-AzureRmADUser.md)

[Get-AzureRmADServicePrincipal](./Get-AzureRmADServicePrincipal.md)

[Get-AzureRmADGroupMember](./Get-AzureRmADGroupMember.md)
