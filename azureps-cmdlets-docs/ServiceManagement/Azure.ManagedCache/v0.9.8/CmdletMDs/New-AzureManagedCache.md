---
external help file: Microsoft.Azure.Commands.ManagedCache.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureManagedCache

## SYNOPSIS
Creates an Azure cache.

## SYNTAX

```
New-AzureManagedCache [-Name] <String> [-Location] <String> [-Sku <CacheServiceSkuType>]
 [-Profile <AzureProfile>] [-Memory <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureManagedCache** cmdlet creates an Azure Cache in your Azure account and returns an object that represents the new Azure Cache.
An Azure Cache is a secure, dedicated cache that provides extremely fast access to data.
This distributed, in-memory, scalable solution enables you to build highly scalable and responsive applications.
For more information about Azure Cache, see Azure Cachehttp://azure.microsoft.com/en-us/services/cache/.

## EXAMPLES

### Example 1: Create an Azure Cache
```
PS C:\>New-AzureManagedCache -Name "ContosoCache" -Location "West Europe"
```

This command creates an Azure Cache named ContosoCache in the West Europe Azure data center.
It uses the default values for the Sku and Memory parameters, which are Basic and 128MB.

### Example 2: Create a premium Azure
```
PS C:\>New-AzureManagedCache -Name "ContosoAppCache" -Location "West Europe" -Sku Premium -Memory 150GB
```

This command creates the largest available Azure Cache.

## PARAMETERS

### -Name
Specifies a name for the Azure Cache.
The name can include only lower-case letters and numbers, and it must begin with a lower-case letter.
The name must be unique.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the location of the Azure Cache.
Enter an Azure data center location, such as "North Central US" or "West Europe".
Use the Get-AzureLocation cmdlet to find a location that supports Azure Cache.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
Specifies the tier of the Azure Cache.
).
The default value is Basic.
Valid values are: 

- Basic (128MB - 1GB) 
- Standard (1GB - 10GB) 
- Premium (5GB - 150GB)

```yaml
Type: CacheServiceSkuType
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Memory
Specifies the size of the Azure Cache.
The cache size may affect the cost of the service.
Enter a value followed by "MB" or "GB", such as "128MB" or "8GB".
This value must be compatible with the value of the *Sku* parameter.
The default value is the lowest value in the range specified by the *Sku* parameter.
The following are some considerations:

- When the value of *Sku* is Basic, the value of *Memory* must be divisible by 128MB. 
- When the value of *Sku* is Standard, the value of *Memory* must be divisible by 1GB. 
- When the value of *Sku* is Premium, the value of *Memory* must be divisible by 5GB.

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

### Microsoft.Azure.Commands.ManagedCache.Models .PSCacheService

## NOTES
* Use Add-AzureAccount or Import-AzurePublishSettingsFile to make your Azure account available to Windows PowerShell before you use this cmdlet. For more information, see How to install and configure Azure PowerShellhttp://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/.

## RELATED LINKS

[Get-AzureManagedCache](.\Get-AzureManagedCache.md)

[Remove-AzureManagedCache](.\Remove-AzureManagedCache.md)

[Set-AzureManagedCache](.\Set-AzureManagedCache.md)

[Get-AzureManagedCacheAccessKey](.\Get-AzureManagedCacheAccessKey.md)

[New-AzureManagedCacheAccessKey](.\New-AzureManagedCacheAccessKey.md)

