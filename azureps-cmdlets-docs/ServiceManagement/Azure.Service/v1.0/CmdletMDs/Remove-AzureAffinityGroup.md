---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureAffinityGroup.md
schema: 2.0.0
---

# Remove-AzureAffinityGroup

## SYNOPSIS
Deletes an affinity group in a subscription.

## SYNTAX

```
Remove-AzureAffinityGroup [-Name] <String> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureAffinityGroup** cmdlet deletes an azure_2 affinity group in the current subscription.
You cannot delete an affinity group that has any members.
You must first delete all the members of an affinity group.

## EXAMPLES

### Example 1: Remove an affinity group
```
PS C:\>Remove-AzureAffinityGroup -Name "South01"
```

This command deletes the South01 affinity group in the current subscription.

## PARAMETERS

### -Name
Specifies the name of the affinity group that this cmdlet deletes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

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

### -InformationAction
@{Text=}```yaml
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
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

[Get-AzureAffinityGroup](.\Get-AzureAffinityGroup.md)

[New-AzureAffinityGroup](.\New-AzureAffinityGroup.md)

[Set-AzureAffinityGroup](.\Set-AzureAffinityGroup.md)

