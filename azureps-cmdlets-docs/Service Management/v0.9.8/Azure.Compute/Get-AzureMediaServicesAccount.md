---
external help file: SMAzure_Compute.xml
online version: http://go.microsoft.com/fwlink/?LinkId=324179
schema: 2.0.0
---

# Get-AzureMediaServicesAccount
## SYNOPSIS
Gets the available Azure Media Services accounts.

## SYNTAX

```
Get-AzureMediaServicesAccount [[-Name] <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

To list all the accounts, use the Get-AzureMediaServicesAccount cmdlet.
To get more detailed information about a specific account, use the Get-AzureMediaServicesAccount -Name YourAccountName cmdlet.

## EXAMPLES

### Example 1: List all Media Services accounts
```
PS C:\> Get-AzureMediaServicesAccount
```

This command lists all available Media Services accounts.

### Example 2: Get detailed information about a Media Services account
```
PS C:\> Get-AzureMediaServicesAccount -Name accountname
```

This command displays properties of a Media Services account.

## PARAMETERS

### -Name
The Media Services account name.

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

[How to use Azure PowerShell for Media Services](http://go.microsoft.com/fwlink/?LinkId=324179)

