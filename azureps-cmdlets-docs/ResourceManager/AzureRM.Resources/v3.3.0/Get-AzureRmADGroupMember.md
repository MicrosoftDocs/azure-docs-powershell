---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: 52C5CD8B-2489-4FE6-9F33-B3350531CD8E
online version: 
schema: 2.0.0
---

# Get-AzureRmADGroupMember

## SYNOPSIS
Get group members.

## SYNTAX

```
Get-AzureRmADGroupMember [-GroupObjectId <Guid>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

## DESCRIPTION
The **Get-AzureRmADGroupMember** cmdlet gets group members.

## EXAMPLES

### Example 1: Filter group members using group object ID

```
PS C:\> Get-AzureRmADGroupMember -GroupObjectId 85F89C90-780E-4AA6-9F4F-6F268D322EEE
```

This command gets group members with ID 85F89C90-780E-4AA6-9F4F-6F268D322EEE.

## PARAMETERS

### -GroupObjectId
Specifies the object ID of the group that this cmdlet gets.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmADUser](./Get-AzureRmADUser.md)

[Get-AzureRmADServicePrincipal](./Get-AzureRmADServicePrincipal.md)

[Get-AzureRmADGroupMemberMember](./Get-AzureRmADGroupMemberMember.md)
