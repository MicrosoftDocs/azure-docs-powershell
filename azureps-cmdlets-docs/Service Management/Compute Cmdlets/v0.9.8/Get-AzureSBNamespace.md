---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Get-AzureSBNamespace
## SYNOPSIS
Gets the namespace.

## SYNTAX

```
Get-AzureSBNamespace [[-Name] <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Get-AzureSBNamespace cmdlet returns the Service Bus service namespaces associated with the current subscription.

## EXAMPLES

### 1: Get the Service Bus namespace
```
PS C:\>Get-AzureSBNamespace
```

This example gets the Service Bus service namespaces associated with the current subscription.

## PARAMETERS

### -Name
Specifies the name of a Service Bus namespace to look for.

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

[Get-AzureSBLocation](bff960ab-8d2e-43e7-879c-fc13559394df)

