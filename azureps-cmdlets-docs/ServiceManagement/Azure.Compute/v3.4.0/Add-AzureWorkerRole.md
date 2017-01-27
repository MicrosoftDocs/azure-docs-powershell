---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 8632A865-D4CC-4AE5-8307-055CDD776D26
online version: 
schema: 2.0.0
---

# Add-AzureWorkerRole

## SYNOPSIS
Creates required files and configuration for a custom worker role.

## SYNTAX

```
Add-AzureWorkerRole [-TemplateFolder <String>] [-Name <String>] [-Instances <Int32>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Add-AzureWorkerRole** cmdlet creates required files and configuration, sometimes referred to as scaffolding, for a custom worker role.

## EXAMPLES

### Example 1: Create a single instance worker role
```
PS C:\> Add-AzureWorkerRole -Name MyWorkerRole
```

This example adds scaffolding for a single worker role named MyWorkerRole to the current application.

### Example 2: Create a multiple instance worker role
```
PS C:\> Add-AzureWorkerRole MyWorkerRole -I 2
```

This example adds scaffolding for a new worker role named MyWorkerRole to the current application, with a role instance count of 2.

### Example 3: Create worker role with custom scaffolding
```
PS C:\> Add-AzureWorkerRole MyWorkerRole -TemplateFoldr .\MyWorkerRoleTemplate
```

This example creates a worker role with custom scaffolding.

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
This value determines the folder name that contains the scaffolding for the custom application that will be hosted in the worker role.
The default is WorkerRolenumber, where number is the number of worker roles in the service.

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

### -TemplateFolder
Specifies the scaffolding template folder to be used to create the worker role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureWebRole](./Add-AzureWebRole.md)

[New-AzureRoleTemplate](./New-AzureRoleTemplate.md)


