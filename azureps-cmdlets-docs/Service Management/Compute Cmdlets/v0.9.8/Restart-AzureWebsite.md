---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Restart-AzureWebsite
## SYNOPSIS
Stops and then restarts the specified website.

## SYNTAX

```
Restart-AzureWebsite [[-Name] <String>] [-PassThru] [-Slot <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Restart-AzureWebsite cmdlet stops and then restarts the specified website.

## EXAMPLES

### 1: Restart a website
```
PS C:\>Restart-AzureWebsite â€"Name MyWebsite
```

This example restarts a website named MyWebsite.

## PARAMETERS

### -Name
Specifies the name of the Azure website to restart.

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

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Start-AzureWebsite](d6ee400f-4a92-4f2f-83bb-70188bb2000d)

[Remove-AzureWebsite](3997c3b8-37ce-4135-a17d-63ae3bdd8e74)

