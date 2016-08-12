---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Save-AzureWebsiteLog
## SYNOPSIS
Downloads and saves the logs for a specified website.

## SYNTAX

```
Save-AzureWebsiteLog [[-Name] <String>] [[-Output] <String>] [-PassThru] [-Slot <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Save-AzureWebsiteLog cmdlet downloads the logs for a specified website.

## EXAMPLES

### 1: Download and save logs for a website
```
PS C:\>Save-AzureWebsiteLogs -Name mySite -Output .\logs.zip
```

This example downloads the runtime and deployment logs for website 'mySite' to the file 'logs.zip' in the current directory.

## PARAMETERS

### -Name
Specifies the name of the website.

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

### -Output
Specifies the path to store the downloaded file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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
Specifies the slot name.

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

[Get-AzureWebsiteDeployment](245ccf61-fa3e-41c8-98f7-0022e8f2ef3a)

[Restore-AzureWebsiteDeployment](05b24030-ff70-48d2-8bed-d17d0451d4ca)

