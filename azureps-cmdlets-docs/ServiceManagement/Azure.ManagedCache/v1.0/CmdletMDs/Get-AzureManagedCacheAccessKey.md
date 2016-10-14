---
external help file: Microsoft.Azure.Commands.ManagedCache.dll-Help.xml
online version: .\New-AzureManagedCacheAccessKey.md
schema: 2.0.0
---

# Get-AzureManagedCacheAccessKey

## SYNOPSIS
Gets the access keys for an azure_2 Cache.

## SYNTAX

```
Get-AzureManagedCacheAccessKey [-Name] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureManagedCacheAccessKey** cmdlet gets the primary and secondary access keys for an azure_2 Cache.
You can use these keys to allow clients, such as web applications, to access to your azure_2 Cache.
Typically, you use the primary key, but use the secondary key to avoid delays while the primary key is being regenerated.
To get new access keys, use the New-AzureManagedCacheAccessKey cmdlet.
An azure_2 Cache is a secure, dedicated cache that provides extremely fast access to data.
This distributed, in-memory, scalable solution enables you to build highly scalable and responsive applications.
For more information about azure_2 Cache, see Azure Cachehttp://azure.microsoft.com/en-us/services/cache/.

## EXAMPLES

### Example 1: Get the access key for an Azure Cache
```
PS C:\>Get-AzureManagedCacheAccessKey -Name "ContosoCache"
```

This command gets the access key for the azure_2 Cache named ContosoCache.

## PARAMETERS

### -Name
Specifies the name of the azure_2 Cache.
This parameter value is case-sensitive.
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

### Microsoft.Azure.Management.ManagedCache.Models.CachingKeysResponse

## NOTES

## RELATED LINKS

[New-AzureManagedCacheAccessKey](.\New-AzureManagedCacheAccessKey.md)

[New-AzureManagedCache](.\New-AzureManagedCache.md)

[Get-AzureManagedCache](.\Get-AzureManagedCache.md)

[Set-AzureManagedCache](.\Set-AzureManagedCache.md)

[Remove-AzureManagedCache](.\Remove-AzureManagedCache.md)

