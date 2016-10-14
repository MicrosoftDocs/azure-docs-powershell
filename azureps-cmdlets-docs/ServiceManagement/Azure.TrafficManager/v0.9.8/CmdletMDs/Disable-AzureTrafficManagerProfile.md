---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=398282
schema: 2.0.0
---

# Disable-AzureTrafficManagerProfile

## SYNOPSIS
Disables a Traffic Manager profile.

## SYNTAX

```
Disable-AzureTrafficManagerProfile [-Name] <String> [-PassThru] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-AzureTrafficManagerProfile** cmdlet disables a Microsoft Azure Traffic Manager profile.
You can use the *PassThru* parameter to display whether the operation succeeds.

## EXAMPLES

### Example 1: Disable a Traffic Manager profile and display the results
```
PS C:\>Disable-AzureTrafficManagerProfile -Name "MyProfile" -PassThru
True
```

This command disables the Traffic Manager profile named MyProfile.
The command specifies the *PassThru* parameter to display whether the command succeeded.

### Example 2: Disable a Traffic Manager profile and display no results
```
PS C:\>Disable-AzureTrafficManagerProfile -Name "MyProfile"
```

This command disables the Traffic Manager profile named MyProfile but does not display whether the command succeeded.

## PARAMETERS

### -Name
Specifies the name of the Traffic Manager profile to disable.

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
In-memory profile.```yaml
Type: AzureProfile
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

[Enable-AzureTrafficManagerProfile](.\Enable-AzureTrafficManagerProfile.md)

[Get-AzureTrafficManagerProfile](.\Get-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](.\New-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](.\Remove-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](.\Set-AzureTrafficManagerProfile.md)

