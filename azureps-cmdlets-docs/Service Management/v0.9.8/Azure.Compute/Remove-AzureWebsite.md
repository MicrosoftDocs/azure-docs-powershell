---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Remove-AzureWebsite
## SYNOPSIS
Removes the specified website from Azure.

## SYNTAX

```
Remove-AzureWebsite [[-Name] <String>] [-Force] [-Slot <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Remove-AzureWebsite cmdlet removes the specified website from Azure, either with or without a prompt for confirmation.

## EXAMPLES

### 1: Remove the current website
```
PS C:\>Remove-AzureWebsite
```

This example removes the website in Azure associated with the current directory

### 2: Remove a website without confirmation
```
PS C:\>Remove-AzureWebsite -Name mySite -Force
```

This example deletes the website named 'mySite' without prompting for confirmation.

## PARAMETERS

### -Force
If specified, deletes the specified website without prompting for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the website to delete.

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

### -Slot
Specifies the slot name of the website.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

