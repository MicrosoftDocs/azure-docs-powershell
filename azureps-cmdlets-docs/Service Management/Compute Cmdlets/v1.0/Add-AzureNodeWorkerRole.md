---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Add-AzureNodeWorkerRole
## SYNOPSIS
Creates the required files and folders for a Node.js application to be hosted in the cloud via node.exe

## SYNTAX

```
Add-AzureNodeWorkerRole [[-Name] <String>] [[-Instances] <Int32>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Add-AzureNodeWorkerRole cmdlet creates the required files and folders (sometimes referred to as scaffolding) for a Node.js application to be hosted in the cloud via node.exe.

## EXAMPLES

### 1: Single instance worker role
```
PS C:\>Add-AzureWorkerRole MyWorkerRole
```

This example adds scaffolding for a single worker role named MyWorkerRole to the current application.

### 2: Multiple instance worker role
```
PS C:\>Add-AzureNodeWorkerRole MyWorkerRole -I 2
```

This example adds scaffolding for a single worker role named MyWorkerRole to the current application, with a role instance count of 2.

## PARAMETERS

### -Instances
Specifies the number of role instances for this worker role.
Default is 1.

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
The value determines the folder name that contains the scaffolding for the node.js service hosted in the worker role.
Default is WorkerRole1.

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

[Add-AzureNodeWebRole](72be1e83-84e2-49fc-aa52-b3d3dd0490a3)

[New-AzureServiceProject](68b3e4a9-7aff-4274-bd8c-0f664cb6e65d)

