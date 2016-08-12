---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Add-AzureCacheWorkerRole
## SYNOPSIS
Adds a dedicated cache worker role to the current service.

## SYNTAX

```
Add-AzureCacheWorkerRole [[-Name] <String>] [[-Instances] <Int32>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Add-AzureCacheWorkerRole cmdlet adds a dedicated cache worker role to the current service.

## EXAMPLES

### Example 1: Add a cache role
```
PS C:\>Add-AzureCacheWorkerRole
```

This command adds a cache role to the current service.

## PARAMETERS

### -Instances
Specifies the number of worker role instances to devote to the cache worker role.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: i

Required: False
Position: 2
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the cache worker role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

Required: False
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AzureMemcacheRole](a836221d-899c-40af-b2f7-0629c13e3de3)

[Add-AzureNodeWebRole](72be1e83-84e2-49fc-aa52-b3d3dd0490a3)

[Add-AzurePHPWebRole](6dd8d854-912d-4281-977c-ff3ec15ccf51)

