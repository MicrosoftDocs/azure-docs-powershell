---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# New-AzureRoleTemplate
## SYNOPSIS
Creates web and worker role templates.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureRoleTemplate [-Web] [[-Output] <String>]
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureRoleTemplate [-Worker] [[-Output] <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The New-AzureRoleTemplate cmdlet creates web and worker role templates.

## EXAMPLES

### 1: Create a web role template
```
PS C:\>New-AzureRoleTemplate -Web
```

This example creates a new web role template in a folder named WebRoleTemplate in the current directory.

### 2: Create a worker role template
```
PS C:\>New-AzureRoleTemplate -Worker
```

This example creates a new worker role template in a folder named WebRoleTemplate in the current directory.

### 3: Create a role template in a custom directory
```
PS C:\>New-AzureRoleTemplate -Web -Output C:\MyWebRoleTemplate
```

This example creates a new web role template in directory named MyWebRoleTemplate, instead of in the current directory.

## PARAMETERS

### -Output
Specifies the output path of generated template.
\<Unclear to meâ€¦is this where you want to store the template that the cmdlet creates?
Seems to be based on the example.\>

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

### -Web
Specifies that you want to create a web role template.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Worker
Specifies that you want to create a worker role template.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
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

[Add-AzureWebRole](e973ae60-0350-4440-a0ea-03ca4da295c5)

[Add-AzureWorkerRole](77af980e-7b69-46b9-af3c-6d586710eff8)

