---
external help file: Microsoft.Azure.Commands.ManagedCache.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureManagedCache

## SYNOPSIS
Removes an azure_2 Cache.

## SYNTAX

```
Remove-AzureManagedCache [-Name] <String> [-PassThru] [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureManagedCache** cmdlet removes an azure_2 Cache and all of the data in the Cache.
It returns $True if the operation was successful and $False if it failed.
By default, **Remove-AzureManagedCache** will prompt you for confirmation before it removes the azure_2 Cache, but you can use the *Force* parameter to suppress the prompt.
An azure_2 Cache is a secure, dedicated cache that provides extremely fast access to data.
This distributed, in-memory, scalable solution enables you to build highly scalable and responsive applications.
For more information about azure_2 Cache, see Azure Cachehttp://azure.microsoft.com/en-us/services/cache/.

## EXAMPLES

### Example 1: Remove an Azure Cache
```
PS C:\>Remove-AzureManagedCache -Name "ContosoCache"
Confirm
Are you sure you want to perform this action? 
Performing the operation "Delete" on target "ContosoCache".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 
 Y

True
```

This command removes the azure_2 Cache named ContosoCache.
The command prompts for confirmation before the cmdlet removes the Cache.
It returns a value of $True to indicate that the Cache was removed.

### Example 2: Remove all test caches
```
PS C:\>Get-AzureManagedCache | Where-Object Name -like Test* | Remove-AzureManagedCache -Force
```

This command removes all azure_2 Caches that have names that begin with Test.
It uses the Get-AzureManagedCache cmdlet to get the azure_2 Caches in your account.
It pipes them to the Where-Object cmdlet, which returns only the azure_2 Caches that have names that begin with Test.
Then, it pipes the test caches to the **Remove-AzureManagedCache** cmdlet with the *Force* parameter, which removes them without prompting for confirmation.

## PARAMETERS

### -Name
Specifies the name of the azure_2 Cache to remove.
The parameter value is case-sensitive.
Wildcard characters are not permitted.

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
passthru

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

### -Force
ps_force

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Boolean

## NOTES
* Use the Add-AzureAccount or Import-AzurePublishSettingsFile cmdlet to make your azure_2 account available to wps_2 before using this cmdlet. For more information, see How to install and configure Azure PowerShellhttp://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/.

## RELATED LINKS

[Azure Cache](http://azure.microsoft.com/en-us/services/cache/)

[How to install and configure Azure PowerShell](http://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/)

[Get-AzureManagedCache](.\Get-AzureManagedCache.md)

[New-AzureManagedCache](.\New-AzureManagedCache.md)

[Set-AzureManagedCache](.\Set-AzureManagedCache.md)

[Get-AzureManagedCacheAccessKey](.\Get-AzureManagedCacheAccessKey.md)

[New-AzureManagedCacheAccessKey](.\New-AzureManagedCacheAccessKey.md)

