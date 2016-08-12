---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Add-AzureWorkerRole
## SYNOPSIS
Creates required files and configuration (sometimes referred to as scaffolding) for a custom worker role.

## SYNTAX

```
Add-AzureWorkerRole [[-Name] <String>] [[-Instances] <Int32>] [[-TemplateFolder] <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Add-AzureWorkerRole cmdlet creates required files and configuration (sometimes referred to as scaffolding) for a custom worker role.

## EXAMPLES

### 1: Create a single instance worker role
```
PS C:\>Add-AzureWorkerRole -Name MyWorkerRole
```

This example adds scaffolding for a single worker role named MyWorkerRole to the current application.

### 2: Create a multiple instance worker role
```
PS C:\>Add-AzureWorkerRole MyWorkerRole -I 2
```

This example adds scaffolding for a new worker role named MyWorkerRole to the current application, with a role instance count of 2.

### 3: Create worker role with custom scaffolding
```
PS C:\>Add-AzureWorkerRole MyWorkerRole -TemplateFoldr .\MyWorkerRoleTemplate
```

This example creates a worker role with custom scaffolding.

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
This value determines the folder name that contains the scaffolding for the custom application that will be hosted in the worker role.
The default is WorkerRolenumber, where number is the number of worker roles in the service.

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

### -TemplateFolder
Specifies the scaffolding template folder to be used to create the worker role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureWebRole](e973ae60-0350-4440-a0ea-03ca4da295c5)

[New-AzureRoleTemplate](03fbb075-4258-4eb3-a5d1-3ae0f599e361)

