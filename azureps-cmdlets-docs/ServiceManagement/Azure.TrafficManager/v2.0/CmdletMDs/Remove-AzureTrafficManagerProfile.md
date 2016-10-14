---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=398286
schema: 2.0.0
---

# Remove-AzureTrafficManagerProfile

## SYNOPSIS
Removes a Traffic Manager profile.

## SYNTAX

```
Remove-AzureTrafficManagerProfile [-Name] <String> [-Force] [-PassThru] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureTrafficManagerProfile** cmdlet removes a Microsoft Azure Traffic Manager profile from the current subscription.

## EXAMPLES

### Example 1: Remove a Traffic Manager profile
```
PS C:\>Remove-AzureTrafficManagerProfile -Name "MyProfile"
```

This command removes the Traffic Manager profile named MyProfile.

### Example 2: Remove a Traffic Manager profile
```
PS C:\>Remove-AzureTrafficManagerProfile -Name "MyProfile" -Force -PassThru
```

This command removes the Traffic Manager profile named MyProfile without prompting you for confirmation, and returns the results.

## PARAMETERS

### -Name
Specifies the name of the Traffic Manager profile to delete.

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns $True if the operation succeeded; otherwise, $False.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
@{Text=}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean
This cmdlet generates $True or $False.
If the operation is successful and if you specify the *PassThru* parameter, this cmdlet returns a value of $True.

## NOTES

## RELATED LINKS

[Disable-AzureTrafficManagerProfile](.\Disable-AzureTrafficManagerProfile.md)

[Enable-AzureTrafficManagerProfile](.\Enable-AzureTrafficManagerProfile.md)

[Get-AzureTrafficManagerProfile](.\Get-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](.\New-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](.\Set-AzureTrafficManagerProfile.md)

