---
external help file: Microsoft.Azure.Commands.ManagedCache.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureManagedCacheAccessKey

## SYNOPSIS
Creates access keys for an Azure Cache.

## SYNTAX

```
New-AzureManagedCacheAccessKey [-Name] <String> [[-KeyType] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureManagedCacheAccessKey** cmdlet creates primary or secondary access keys for an Azure Cache.
When you create an Azure Cache, it includes a set of access keys.
Use the Get-AzureManagedCacheAccessKey cmdlet to get the current access keys.
You can use these keys to allow clients, such as web applications, to access to your Azure Cache.
An Azure Cache is a secure, dedicated cache that provides extremely fast access to data.
This distributed, in-memory, scalable solution enables you to build highly scalable and responsive applications.
For more information about Azure Cache, see Azure Cachehttp://azure.microsoft.com/en-us/services/cache/.

## EXAMPLES

### Example 1: Create a new primary key
```
PS C:\>New-AzureManagedCacheAccessKey -Name "ContosoCache"
```

This command creates a new primary key for the Azure Cache named ContosoCache.

### Example 2: Create a new secondary key
```
PS C:\>New-AzureManagedCacheAccessKey -Name "ContosoCache" -KeyType Secondary
```

This command creates a new secondary key for the Azure Cache named ContosoCache.

### Example 3: Create new access keys
```
PS C:\>'Primary', 'Secondary' | ForEach-Object {New-AzureManagedCacheAccessKey -Name "ContosoCache" -KeyType $_}
```

This command creates new primary and secondary keys for the Azure Cache named ContosoCache.

## PARAMETERS

### -Name
Specifies the name of Azure Cache access key to generate keys.
The parameter value is case-sensitive.

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

### -KeyType
Specifies the type of key to create.
The default value is Primary.
You generally will use the primary key, but use the secondary key to avoid delays while the primary key is regenerated.
Valid values are: 

- Primary
- Secondary

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

### Microsoft.Azure.Management.ManagedCache.Models.CachingKeysResponse

## NOTES

## RELATED LINKS

[Get-AzureManagedCacheAccessKey](.\Get-AzureManagedCacheAccessKey.md)

[Get-AzureManagedCache](.\Get-AzureManagedCache.md)

[New-AzureManagedCache](.\New-AzureManagedCache.md)

[Remove-AzureManagedCache](.\Remove-AzureManagedCache.md)

[Set-AzureManagedCache](.\Set-AzureManagedCache.md)

