---
external help file: Microsoft.Azure.Commands.ManagedCache.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureManagedCache

## SYNOPSIS
Changes the properties of an azure_2 Cache.

## SYNTAX

```
Set-AzureManagedCache [-Name] <String> [-Sku <CacheServiceSkuType>] [-Force] [-Profile <AzureSMProfile>]
 [-Memory <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureManagedCache** cmdlet changes the properties of an azure_2 Cache and returns an object that represents the cache with the changes.
Use the *Name* and *Location* parameters to identify the azure_2 Cache, and the *Sku* and *Memory* parameters to change its properties.
An azure_2 Cache is a secure, dedicated cache that provides extremely fast access to data.
This distributed, in-memory, scalable solution enables you to build highly scalable and responsive applications.
For more information about azure_2 Cache, see Azure Cachehttp://azure.microsoft.com/en-us/services/cache/.
WARNING: When you change the *SKU* of an azure_2 Cache, all data in the cache is deleted and a new, empty azure_2 Cache is created for you with the same name and location.

## EXAMPLES

### Example 1: Change the size of an Azure Cache
```
PS C:\>Set-AzureManagedCache -Name "ContosoCache" -Location "West Europe" -Memory 256MB
```

This command increases the size of the azure_2 Cache named ContosoCache to 256 MB.

### Example 2: Change the SKU of an Azure Cache
```
PS C:\>Set-AzureManagedCache -Name "ContosoCache" -Location "West Europe" -Sku Standard -Size 10GB
Confirm
Are you sure you want to perform this action? 
Performing the operation "Delete" on target "ContosoCache".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

This command changes the SKU of the azure_2 Cache named ContosoCache from Basic to Standard and the Size to 10 GB.

## PARAMETERS

### -Name
Specifies the name of the azure_2 Cache.
The parameter value is case-sensitive.
You cannot use this cmdlet to change the name of an azure_2 Cache.

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
Specifies the tier of the azure_2 Cache.

psdx_paramvalues

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

### -Memory
Specifies the new size of the azure_2 Cache.
The cache size might affect the cost of the service.
Enter a value followed by MB or GB, such as 128MB or 8GB.
This value must be compatible with the Sku of the azure_2 Cache.
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

### Microsoft.Azure.Commands.ManagedCache.Models.PsCacheService

## NOTES
* Use the Add-AzureAccount or Import-AzurePublishSettingsFile cmdlet to make your azure_2 account available to wps_2 before using this cmdlet. For more information, see How to install and configure Azure PowerShellhttp://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/.

## RELATED LINKS

[How to install and configure Azure PowerShell](http://azure.microsoft.com/en-us/documentation/articles/install-configure-powershell/)

[Azure Cache](http://azure.microsoft.com/en-us/services/cache/)

[Get-AzureManagedCache](.\Get-AzureManagedCache.md)

[New-AzureManagedCache](.\New-AzureManagedCache.md)

[Remove-AzureManagedCache](.\Remove-AzureManagedCache.md)

