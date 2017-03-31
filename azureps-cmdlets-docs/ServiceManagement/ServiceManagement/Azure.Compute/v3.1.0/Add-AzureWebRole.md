---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: FB5CD696-108D-4A3E-8983-1C6562E8795A
online version: 
schema: 2.0.0
---

# Add-AzureWebRole

## SYNOPSIS
Adds a web worker role.

## SYNTAX

```
Add-AzureWebRole [[-TemplateFolder] <String>] [[-Name] <String>] [[-Instances] <Int32>]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Add-AzureWebRole** cmdlet adds a web worker role.

## EXAMPLES

### Example 1: Add a default role
```
PS C:\> Add-AzureWebRole
```

This command add web role that has the default configuration of Webrole1 as the name and a single instance.

### Example 2: Add a role with a name
```
PS C:\> Add-AzureWebRole -Name "MyWebRole"
```

This command adds a single web role named MyWebRole to the current application.

### Example 3: Add a role with a name and instance count
```
PS C:\> Add-AzureWebRole -Name "MyWebRole" -Instance 2
```

This command adds a web role named MyWebRole to the current application.
The cmdlet has a role instance count of 2.

### Example 4: Add a role with a name and template
```
PS C:\> Add-AzureWebRole -Name "MyWebRole" -TemplateFolder ".\MyWebTemplateFolder"
```

This command adds a single web role named MyWebRole to the current application.
The command specifies a folder named MyWebTemplateFolder as a scaffolding template.

## PARAMETERS

### -TemplateFolder
Specifies the template folder.

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

### -Name
Specifies the name of the web role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instances
Specifies the number of instances.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: i

Required: False
Position: 1
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

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

[Add-AzureWorkerRole](./Add-AzureWorkerRole.md)

[New-AzureRoleTemplate](./New-AzureRoleTemplate.md)


