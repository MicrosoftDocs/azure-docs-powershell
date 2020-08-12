---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: C2DAFB2C-A58B-406C-8349-8728771B279E
online version: 
schema: 2.0.0
---

# Add-AzureNodeWebRole

## SYNOPSIS
Creates required files and folders for a Node.js application.

## SYNTAX

```
Add-AzureNodeWebRole [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Add-AzureNodeWebRole** creates required files and folders, sometimes referred to as scaffolding, for a Node.js application to be hosted in the cloud via IIS.

## EXAMPLES

### Example 1: Single instance web role
```
PS C:\> Add-AzureNodeWebRole -Name MyWebRole
```

This example adds scaffolding for a single web role named **MyWebRole** to the current application.

### Example 2: Multiple instance web role
```
PS C:\> Add-AzureNodeWebRole MyWebRole -I 2
```

This example adds scaffolding for a new web role named **MyWebRole** to the current application, with a role instance count of 2.

## PARAMETERS

### -Instances
Specifies the number of role instances for this web role.
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
Specifies the name of the web role.
It also determines the name of the directory that contains the scaffolding for the node.js application that will be hosted in the web role.
The default is WebRole#, where # indicates the number of web roles in the service.

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

[Add-AzureNodeWorkerRole](./Add-AzureNodeWorkerRole.md)

[New-AzureServiceProject](./New-AzureServiceProject.md)


