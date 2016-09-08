---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Start-AzureWebsite
## SYNOPSIS
Starts the specified website.

## SYNTAX

```
Start-AzureWebsite [[-Name] <String>] [-PassThru] [-Slot <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Start-AzureWebsite cmdlet starts a specified website running in Azure.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the website to start.

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

### -PassThru
@{Text=}

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

[Restart-AzureWebsite](b1bbfd6e-a344-4d15-bb77-292a83034890)

[Stop-AzureWebsite](62c5de93-e58b-4e57-85d0-8b7e75df1f31)

