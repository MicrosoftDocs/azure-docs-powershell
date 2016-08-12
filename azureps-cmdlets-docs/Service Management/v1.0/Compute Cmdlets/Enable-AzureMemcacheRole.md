---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Enable-AzureMemcacheRole
## SYNOPSIS
Enable memcached for the specified web role, configured to communicate with the specified dedicated cache role.

## SYNTAX

```
Enable-AzureMemcacheRole [[-RoleName] <String>] [[-CacheWorkerRoleName] <String>] [-PassThru]
 [[-CacheRuntimeVersion] <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Enable-AzureMemcacheRole cmdlet enables memcached for the specified web role, configured to communicate with the specified dedicated cache role

## EXAMPLES

### 1: Enable caching in a web role
```
PS C:\>Enable-AzureMemcacheRole WebRole1 WorkerRole1
```

This example enables memcached in a web role named WebRole1, using a dedicated caching role named WorkerRole1.

## PARAMETERS

### -CacheRuntimeVersion
Specifies the cache runtime version.

```yaml
Type: String
Parameter Sets: (All)
Aliases: cv

Required: False
Position: 4
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CacheWorkerRoleName
Specifies the name of the dedicated cache worker role, created with the Add-AzureCacheWorkerRole cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: cn

Required: False
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleName
Specifies the name of the web role that will use the cache.

```yaml
Type: String
Parameter Sets: (All)
Aliases: rn

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureCacheWorkerRole](f82034ef-883e-456e-8b8a-3502f8a56b85)

[Add-AzureNodeWebRole](72be1e83-84e2-49fc-aa52-b3d3dd0490a3)

[Add-AzurePHPWebRole](6dd8d854-912d-4281-977c-ff3ec15ccf51)

