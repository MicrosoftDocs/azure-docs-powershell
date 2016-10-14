---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureStoreAddOn

## SYNOPSIS
Removes an existing add-on instance.

## SYNTAX

```
Remove-AzureStoreAddOn [-Name] <String> [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

Removes an existing add-on instance from the current subscription.

## EXAMPLES

### Example 1
```
PS C:\>Remove-AzureStoreAddOn MyAddOn
```

This example removes an add-on named MyAddOn from the current subscription.

## PARAMETERS

### -Name
Specifies the name of the add-on instance to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
@{Text=}

```yaml
Type: SwitchParameter
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

[Get-AzureStoreAddOn](.\Get-AzureStoreAddOn.md)

[New-AzureStoreAddOn](.\New-AzureStoreAddOn.md)

[Set-AzureStoreAddOn](.\Set-AzureStoreAddOn.md)

