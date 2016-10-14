---
external help file: Microsoft.Azure.Commands.ManagedCache.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureManagedCache

## SYNOPSIS
Gets the azure_2 Caches in your azure_2 account.

## SYNTAX

```
Get-AzureManagedCache [[-Name] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureManagedCache** cmdlet get the azure_2 Caches in your account.
By default, it gets all azure_2 Caches in the account.
To get a particular azure_2 Cache, use the *Name* parameter.
An azure_2 Cache is a secure, dedicated cache that provides extremely fast access to data.
This distributed, in-memory, scalable solution enables you to build highly scalable and responsive applications.
For more information about azure_2 Cache, see Azure Cachehttp://azure.microsoft.com/en-us/services/cache/.

## EXAMPLES

### Example 1: Get all Azure Caches
```
PS C:\>Get-AzureManagedCache
```

This command gets all azure_2 Caches in your account.

### Example 2: Get an Azure Cache by name
```
PS C:\>Get-AzureManagedCache -Name "ContosoCache"
```

This command gets the azure_2 Cache named ContosoCache.

## PARAMETERS

### -Name
Specifies the azure_2 cache.
You need to supply the name of an azure_2 Cache.
This parameter is case-sensitive.
This parameter is optional.
By default, **Get-AzureManagedCache** gets all azure_2 caches in the account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.ManagedCache.Models.PSCacheService

## NOTES
* Before you use this cmdlet, call Add-AzureAccount or Import-AzurePublishSettingsFile to make your azure_2 account available to wps_2. For more information, see How to install and configure Azure PowerShellhttp://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/.

## RELATED LINKS

[New-AzureManagedCache](.\New-AzureManagedCache.md)

[Set-AzureManagedCache](.\Set-AzureManagedCache.md)

[Remove-AzureManagedCache](.\Remove-AzureManagedCache.md)

[Get-AzureManagedCacheAccessKey](.\Get-AzureManagedCacheAccessKey.md)

[New-AzureManagedCacheAccessKey](.\New-AzureManagedCacheAccessKey.md)

