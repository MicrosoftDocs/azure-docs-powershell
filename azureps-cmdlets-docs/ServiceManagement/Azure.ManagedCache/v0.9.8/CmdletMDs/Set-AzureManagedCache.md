---
external help file: Microsoft.Azure.Commands.ManagedCache.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureManagedCache

## SYNOPSIS
Changes the properties of an Azure Cache.

## SYNTAX

```
Set-AzureManagedCache [-Name] <String> [-Sku <CacheServiceSkuType>] [-Force] [-Profile <AzureProfile>]
 [-Memory <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureManagedCache** cmdlet changes the properties of an Azure Cache and returns an object that represents the cache with the changes.
Use the *Name* and *Location* parameters to identify the Azure Cache, and the *Sku* and *Memory* parameters to change its properties.
An Azure Cache is a secure, dedicated cache that provides extremely fast access to data.
This distributed, in-memory, scalable solution enables you to build highly scalable and responsive applications.
For more information about Azure Cache, see Azure Cachehttp://azure.microsoft.com/en-us/services/cache/.WARNING: When you change the *SKU* of an Azure Cache, all data in the cache is deleted and a new, empty Azure Cache is created for you with the same name and location.

## EXAMPLES

### Example 1: Change the size of an Azure Cache
```
PS C:\>Set-AzureManagedCache -Name "ContosoCache" -Location "West Europe" -Memory 256MB
```

This command increases the size of the Azure Cache named ContosoCache to 256 MB.

### Example 2: Change the SKU of an Azure Cache
```
PS C:\>Set-AzureManagedCache -Name "ContosoCache" -Location "West Europe" -Sku Standard -Size 10GB
Confirm
Are you sure you want to perform this action? 
Performing the operation "Delete" on target "ContosoCache".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command changes the SKU of the Azure Cache named ContosoCache from Basic to Standard and the Size to 10 GB.

## PARAMETERS

### -Name
Specifies the name of the Azure Cache.
The parameter value is case-sensitive.
You cannot use this cmdlet to change the name of an Azure Cache.

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

### -Sku
Specifies the tier of the Azure Cache.

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

### -Memory
Specifies the new size of the Azure Cache.
The cache size might affect the cost of the service.
Enter a value followed by "MB" or "GB", such as 128MB or 8GB.
This value must be compatible with the Sku of the Azure Cache.
This parameter has the following considerations: 

- When the value of Sku is Basic, the value of Memory must be divisible by 128MB.
- When the value of Sku is Standard, the value of Memory must be divisible by 1GB.
- When the value of Sku is Premium, the value of Memory must be divisible by 5GB.

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

### Microsoft.Azure.Commands.ManagedCache.Models.PsCacheService

## NOTES
* Use the Add-AzureAccount or Import-AzurePublishSettingsFile cmdlet to make your Azure account available to Windows PowerShell before using this cmdlet. For more information, see How to install and configure Azure PowerShellhttp://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/.

## RELATED LINKS

[How to install and configure Azure PowerShell](http://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/)

[Azure Cache](http://azure.microsoft.com/en-us/services/cache/)

[Get-AzureManagedCache](.\Get-AzureManagedCache.md)

[New-AzureManagedCache](.\New-AzureManagedCache.md)

[Remove-AzureManagedCache](.\Remove-AzureManagedCache.md)

