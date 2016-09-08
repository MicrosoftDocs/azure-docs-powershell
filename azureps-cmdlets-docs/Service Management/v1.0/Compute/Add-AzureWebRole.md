---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Add-AzureWebRole
## SYNOPSIS
Adds a web worker role.

## SYNTAX

```
Add-AzureWebRole [[-Name] <String>] [[-Instances] <Int32>] [[-TemplateFolder] <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Add-AzureWebRole cmdlet adds a web worker role.

## EXAMPLES

### Example 1: Add a default role
```
PS C:\>Add-AzureWebRole
```

This command add web role that has the default configuration of Webrole1 as the name and a single instance.

### Example 2: Add a role with a name
```
PS C:\>Add-AzureWebRole -Name "MyWebRole"
```

This command adds a single web role named MyWebRole to the current application.

### Example 3: Add a role with a name and instance count
```
PS C:\>Add-AzureWebRole -Name "MyWebRole" -Instance 2
```

This command adds a web role named MyWebRole to the current application.
The cmdlet has a role instance count of 2.

### Example 4: Add a role with a name and template
```
PS C:\>Add-AzureWebRole -Name "MyWebRole" -TemplateFolder ".\MyWebTemplateFolder"
```

This command adds a single web role named MyWebRole to the current application.
The command specifies a folder named MyWebTemplateFolder as a scaffolding template.

## PARAMETERS

### -Instances
Specifies the number of instances.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: i

Required: False
Position: 2
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the web role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

Required: False
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateFolder
Specifies the template folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureWorkerRole](77af980e-7b69-46b9-af3c-6d586710eff8)

[New-AzureRoleTemplate](03fbb075-4258-4eb3-a5d1-3ae0f599e361)

