---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Get-AzureServiceProjectRoleRuntime
## SYNOPSIS
Get the runtimes available to install in a role.

## SYNTAX

```
Get-AzureServiceProjectRoleRuntime [[-Runtime] <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

Gets the runtimes available to install in a role.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Runtime
The name of the runtime.
If a runtime specified, only the specific versions of that runtime available to install in your role in Windows Azure will be returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

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

[Add-AzureNodeWebRole](72be1e83-84e2-49fc-aa52-b3d3dd0490a3)

[Add-AzureNodeWorkerRole](97649579-ead5-45c6-8bb3-e718c007e771)

[Set-AzureServiceProjectRole](80fb7e11-389d-4341-9568-e1a1bc1789df)

[Set-AzureServiceProject](c3baa783-e57a-46bd-abe4-6d06130eaaf0)

