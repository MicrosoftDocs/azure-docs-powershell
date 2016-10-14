---
external help file: Microsoft.Azure.Commands.ManagedCache.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureManagedCacheNamedCache

## SYNOPSIS
Updates a named cache in the specified Azure Managed Cache Service instance.

## SYNTAX

```
Set-AzureManagedCacheNamedCache -Name <String> -NamedCache <String> [-ExpiryPolicy <String>]
 [-ExpiryTime <Int32>] [-WithNotifications] [-WithHighAvailability] [-WithoutEviction] [-Force]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureManagedCacheNamedCache** cmdlet updates a named cache in the specified Azure Managed Cache Service instance in your Azure account and returns an object that represents the named cache.

## EXAMPLES

### Example 1: Update a named cache in the Azure Managed Cache Service instance
```
PS C:\>Set-AzureManagedCacheNamedCache -Name "ContosoCache" -NamedCache "ContosoNamedCache"
```

This command updates a named cache named ContosoNamedCache in the Azure Managed Cache Service instance named ContosoCache.
It will update the named cache to use default values.

### Example 2: Update a named cache with all parameters specified
```
PS C:\>Set-AzureManagedCacheNamedCache -Name "ContosoCache" -NamedCache "ContosoNamedCache" -ExpiryPolicy "Sliding" -ExpiryTime 10 -WithNotifications -WithHighAvailability -WithoutEviction
```

This command updates a named cache named ContosoNamedCache in the Azure Managed Cache Service instance named ContosoCache.
It has Notifications and High Availability enabled and Eviction disabled.

## PARAMETERS

### -Name
Specifies the name of the Azure Managed Cache Service instance in which to update a named cache.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NamedCache
Specifies the name of the named cache to update.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryPolicy
Specifies the expiry policy for the named cache.
The default value is Absolute.

Valid values are: 

- Absolute
- Sliding
- Never

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryTime
Specifies the expiry time of the named cache, in minutes.
The default value is 10.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WithHighAvailability
Indicates that high availability is enabled for the named cache.
High availability is supported in the Standard and Premium cache offerings, and is unavailable in the Basic cache offering.

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

### -WithNotifications
Indicates that notifications are enabled for the named cache.
Notifcations are supported in the Standard and Premium cache offerings, and are unavailable in the Basic cache offering.

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

### -WithoutEviction
Indicates that Eviction is disabled.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

## OUTPUTS

### Microsoft.Azure.Commands.ManagedCache.Models.PSCacheServiceWithNamedCaches

## NOTES
* Use the Add-AzureAccount or Import-AzurePublishSettingsFile cmdlet to make your Azure account available to Windows PowerShell before using this cmdlet. For more information, see How to install and configure Azure PowerShellhttp://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/.

## RELATED LINKS

[How to install and configure Azure PowerShell](http://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/)

[Get-AzureManagedCacheNamedCache](.\Get-AzureManagedCacheNamedCache.md)

[New-AzureManagedCacheNamedCache](.\New-AzureManagedCacheNamedCache.md)

[Remove-AzureManagedCacheNamedCache](.\Remove-AzureManagedCacheNamedCache.md)

