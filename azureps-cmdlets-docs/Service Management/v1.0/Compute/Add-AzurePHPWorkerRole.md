---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Add-AzurePHPWorkerRole
## SYNOPSIS
Creates the required files and configuration (sometimes referred to as scaffolding) for a PHP application that will be hosted in Azure through php.exe.

## SYNTAX

```
Add-AzurePHPWorkerRole [[-Name] <String>] [[-Instances] <Int32>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

Creates the required files and configuration (sometimes referred to as scaffolding) for a PHP application that will be hosted in Azure through php.exe.

## EXAMPLES

### 1: Create a worker role with a single instance
```
PS C:\>Add-AzurePHPWorkerRole MyWorkerRole
```

This example adds the required files and configuration for a single worker role named â€œMyWorkerRoleâ€ to the current application.

### 2: Create a worker role with multiple instances
```
PS C:\>Add-AzurePHPWorkerRole MyWorkerRole -I 2
```

This example adds the required files and configuration for a new worker role to the current application, using the name â€œMyWorkerRoleâ€ with a role instance count of 2.

## PARAMETERS

### -Instances
Specifies the number of role instances for this worker role.
The default is 1.

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
Specifies the name of the worker role.
The name determines the folder name that contains the required files and configuration for the PHP service hosted in the worker role.
The default is WorkerRole1.

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

[New-AzureServiceProject](68b3e4a9-7aff-4274-bd8c-0f664cb6e65d)

[Add-AzurePHPWebRole](6dd8d854-912d-4281-977c-ff3ec15ccf51)

