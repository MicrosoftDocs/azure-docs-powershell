---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# New-AzureServiceProject
## SYNOPSIS
Creates the required files and configuration (sometimes referred to as scaffolding) for a new service.

## SYNTAX

```
New-AzureServiceProject [-ServiceName] <String>
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The New-AzureServiceProject cmdlet creates the required files and configuration for a new Azure service in the current directory.

## EXAMPLES

### 1:
```
PS C:\>New-AzureServiceProject MyService1
```

This example creates scaffolding for a new Azure service named â€œMyService1â€ in the current directory.

## PARAMETERS

### -ServiceName
Specifies the name of the service.
It determines the first section of the hostname for your service (for example, name.cloudapp.net), and the directory that will contain your service.
The name can contain only letters, digits, and the dash character (-).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

[Set-AzureServiceProject](c3baa783-e57a-46bd-abe4-6d06130eaaf0)

[Set-AzureServiceProjectRole](80fb7e11-389d-4341-9568-e1a1bc1789df)

