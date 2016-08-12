---
external help file: SMAzure_Compute.xml
online version: 0c2a5092-db45-4ce7-b39b-d1e499b4a867
schema: 2.0.0
---

# Get-AzureWebsiteLog
## SYNOPSIS
Gets logs for the specified website.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureWebsiteLog [[-Name] <String>] [-ListPath] [-Slot <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureWebsiteLog [[-Name] <String>] [[-Path] <String>] [[-Message] <String>] [-Tail] [-Slot <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

Gets log for the specified website.

## EXAMPLES

### Example 1
```
C:\PS>Get-AzureWebsiteLog -Tail
```

This example starts log streaming for all application logs.

### Example 2
```
C:\PS>Get-AzureWebsiteLog -Tail -Path http
```

This example starts log streaming for http logs.

### Example 3
```
C:\PS>Get-AzureWebsiteLog -Tail -Message Error
```

This example starts log streaming and show error logs only.

### Example 4
```
C:\PS>Get-AzureWebsiteLog -Name MyWebsite -ListPath
```

This example lists all available log paths in the website.

## PARAMETERS

### -ListPath
Specifies whether to list the log paths.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 4
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Message
A string which will be used to filter the log message.
Only logs which contains this string will be retrieved.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The name of the website.

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

### -Path
The path from which the log will be retrieved.
By default it is Root, which means include all the paths.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
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

### -Tail
Specifies whether to stream the logs.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 4
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

[Remove-AzureWebsite](3997c3b8-37ce-4135-a17d-63ae3bdd8e74)

[Start-AzureWebsite](d6ee400f-4a92-4f2f-83bb-70188bb2000d)

