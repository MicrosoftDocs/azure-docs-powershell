---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRoleTemplate

## SYNOPSIS
Creates web and worker role templates.

## SYNTAX

### WebRole
```
New-AzureRoleTemplate [-Web] [[-Output] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### WorkerRole
```
New-AzureRoleTemplate [-Worker] [[-Output] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The **New-AzureRoleTemplate** cmdlet creates web and worker role templates.

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

### -Web
Specifies that you want to create a web role template.

```yaml
Type: SwitchParameter
Parameter Sets: WebRole
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Worker
Specifies that you want to create a worker role template.

```yaml
Type: SwitchParameter
Parameter Sets: WorkerRole
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Output
Specifies the output path of generated template.
\<Unclear to me ¢â‚¬Â¦is this where you want to store the template that the cmdlet creates?
Seems to be based on the example.\>

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureWebRole](.\Add-AzureWebRole.md)

[Add-AzureWorkerRole](.\Add-AzureWorkerRole.md)

