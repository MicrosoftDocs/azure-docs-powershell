---
external help file: SMAzure_Compute.xml
online version: http://go.microsoft.com/fwlink/?LinkId=324179
schema: 2.0.0
---

# Remove-AzureMediaServicesAccount
## SYNOPSIS
Removes the specified Azure Media Services account.

## SYNTAX

```
Remove-AzureMediaServicesAccount [-Name] <String> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Remove-AzureMediaServicesAccount cmdlet removes a Media Services account.

## EXAMPLES

### 1: Delete a Media Services account
```
PS C:\> Remove-AzureMediaServicesAccount -Name "mediaservicesaccount" -Force
```

## PARAMETERS

### -Force
If the â€"Force switch is specified, the deletion is not confirmed.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The Media Services account name.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[How to use Azure PowerShell for Media Services](http://go.microsoft.com/fwlink/?LinkId=324179)

