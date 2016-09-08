---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Add-AzureNodeWebRole
## SYNOPSIS
Creates required files and folders for a Node.js application.

## SYNTAX

```
Add-AzureNodeWebRole [[-Name] <String>] [[-Instances] <Int32>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Add-AzureNodeWebRole creates required files and folders (sometimes referred to as scaffolding) for a Node.js application to be hosted in the cloud via IIS.

## EXAMPLES

### 1: Single instance web role
```
PS C:\>>Add-AzureNodeWebRole -Name MyWebRole
```

This example adds scaffolding for a single web role named MyWebRole to the current application.

### 2: Multiple instance web role
```
PS C:\>Add-AzureNodeWebRole MyWebRole -I 2
```

This example adds scaffolding for a new web role named MyWebRole to the current application, with a role instance count of 2.

## PARAMETERS

### -Instances
The number of role instances for this web role.
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
Specifies the name of the web role.
It also determines the name of the directory that contains the scaffolding for the node.js application that will be hosted in the web role.
The default is WebRole#, where # indicates the number of web roles in the service.

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

[Add-AzureNodeWorkerRole](97649579-ead5-45c6-8bb3-e718c007e771)

[New-AzureServiceProject](68b3e4a9-7aff-4274-bd8c-0f664cb6e65d)

