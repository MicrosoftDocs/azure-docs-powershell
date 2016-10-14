---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Save-AzureServiceProjectPackage

## SYNOPSIS
Packages the service project into Azure cloud package (*.cspkg).

## SYNTAX

```
Save-AzureServiceProjectPackage [-Local] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The **Save-AzureServiceProjectPackage** cmdlet packages the service project into an Azure cloud package (*.cspkg).

## EXAMPLES

### 1: Create a service project package
```
PS C:\>Save-AzureServiceProjectPackage
```

This example creates a *.cspgk for a service project named MyAzureServiceProject.

## PARAMETERS

### -Local
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: l

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Publish-AzureServiceProject](.\Publish-AzureServiceProject.md)

