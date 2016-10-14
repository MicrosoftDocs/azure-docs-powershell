---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=397625
schema: 2.0.0
---

# Remove-AzureAccount

## SYNOPSIS
Deletes an Azure account from Windows PowerShell.

## SYNTAX

```
Remove-AzureAccount [-Name] <String> [-Force] [-PassThru] [-Profile <AzureProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureAccount** cmdlet deletes an Azure account and its subscriptions from the subscription data file in your roaming user profile.
It does not delete the account from Microsoft Azure, or change the actual account in any way.

Using this cmdlet is a lot like logging out of your Azure account.
And, if you want to log into the account again, use the **Add-AzureAccount** or **Import-AzurePublishSettingsFile** to add the account to Windows PowerShell again.

You can also use **Remove-AzureAccount** cmdlet to change the way the Azure PowerShell cmdlets sign into your Azure account.
If your account has both a management certificate from **Import-AzurePublishSettingsFile** and an access token from **Add-AzureAccount**, the Azure PowerShell cmdlets use only the access token; they ignore the management certificate.
To use the management certificate, run **Remove-AzureAccount**.
When **Remove-AzureAccount** finds both a management certificate and an access token, it deletes only the access token, instead of deleting the account.
The management certificate is still there, so account is still available to Windows PowerShell.

This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

## EXAMPLES

### Example 1: Remove an account
```
PS C:\>Remove-AzureAccount -Name admin@contoso.com
```

This command removes the admin@contoso.com from your subscription data file.
When the command completes, the account is no longer available to Windows PowerShell.

## PARAMETERS

### -Name
Specifies the name of the account to remove.
The parameter value is case-sensitive.
Wildcard characters are not supported.

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
Suppresses the confirmation prompt.
By default, **Remove-AzureAccount** prompts you before removing the account from Windows PowerShell.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns True ($true) if the operation succeeded and False ($false) if it failed.
By default, the cmdlet does not return any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
@{Text=}

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You can pipe input to this cmdlet by property name, but not by value.

## OUTPUTS

### None or System.Boolean
If you use the **PassThru** parameter, this cmdlet returns a Boolean value.
Otherwise, it does not return any output.

## NOTES

## RELATED LINKS

[Add-AzureAccount](.\Add-AzureAccount.md)

[Get-AzureAccount](.\Get-AzureAccount.md)

