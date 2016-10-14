---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=397620
schema: 2.0.0
---

# Get-AzureAccount

## SYNOPSIS
Gets Azure accounts that are available to Azure PowerShell.

## SYNTAX

```
Get-AzureAccount [[-Name] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAccount** cmdlet gets the Azure accounts that are available to Windows PowerShell.
To make your accounts available to Windows PowerShell, use the **Add-AzureAccount** or **Import-PublishSettingsFile** cmdlets.

## EXAMPLES

### Example 1: Get all accounts
```
PS C:\>Get-AzureAccount
Name                         ActiveDirectories
----                         -----------------
contosoadmin@outlook.com     {{ ActiveDirectoryTenantId = abcde5cd-bcc3-441a-bd86-e6a...
contosotest1@outlook.com     {{ ActiveDirectoryTenantId = aaeabcde-386c-4466-bf70-794...
```

This command gets all accounts associated with the specified user.

### Example 2: Get an account by name
```
PS C:\>Get-AzureAccount -Name contosoadmin@outlook.com
Name                         ActiveDirectories
----                         -----------------
contosoadmin@outlook.com     {{ ActiveDirectoryTenantId = abcde5cd-bcc3-441a-bd86-e6a...
```

This command gets the ContosoAdmin account.

## PARAMETERS

### -Name
Gets only the specified account.
The default is all accounts that are available to Windows PowerShell.
Enter the account name.
The **Name** value is case-sensitive.
Wildcards are not permitted.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### None
This cmdlet does not return any output.

## NOTES

## RELATED LINKS

[Add-AzureAccount](.\Add-AzureAccount.md)

[Get-AzurePublishSettingsFile](.\Get-AzurePublishSettingsFile.md)

[Import-AzurePublishSettingsFile](.\Import-AzurePublishSettingsFile.md)

[Remove-AzureAccount](.\Remove-AzureAccount.md)

