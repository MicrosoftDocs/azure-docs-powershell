---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: FEFBF1EF-FBCE-45D8-8455-F3F8662F1F36
online version: 
schema: 2.0.0
---

# Add-AzurePHPWorkerRole

## SYNOPSIS
Creates the required files and configuration for a PHP application that will be hosted in Azure through php.exe.

## SYNTAX

```
Add-AzurePHPWorkerRole [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

Creates the required files and configuration, sometimes referred to as scaffolding, for a PHP application that will be hosted in Azure through php.exe.

## EXAMPLES

### Example 1: Create a worker role with a single instance
```
PS C:\> Add-AzurePHPWorkerRole MyWorkerRole
```

This example adds the required files and configuration for a single worker role named MyWorkerRole to the current application.

### Example 2: Create a worker role with multiple instances
```
PS C:\> Add-AzurePHPWorkerRole MyWorkerRole -I 2
```

This example adds the required files and configuration for a new worker role to the current application, using the name MyWorkerRole with a role instance count of 2.

## PARAMETERS

### -Instances
Specifies the number of role instances for this worker role.
The default is 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: i

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the worker role.
The name determines the folder name that contains the required files and configuration for the PHP service hosted in the worker role.
The default is WorkerRole1.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureServiceProject](./New-AzureServiceProject.md)

[Add-AzurePHPWebRole](./Add-AzurePHPWebRole.md)


