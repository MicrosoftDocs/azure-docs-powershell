---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: .\Get-WAPackVM.md
schema: 2.0.0
---

# Get-WAPackVMOSDisk

## SYNOPSIS
Gets operating system disk objects for virtual machines.

## SYNTAX

### Empty (Default)
```
Get-WAPackVMOSDisk [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromId
```
Get-WAPackVMOSDisk [[-ID] <Guid>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackVMOSDisk [[-Name] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
ps_redir_wap This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type (get-module azure).version.

The **Get-WAPackVMOSDisk** cmdlet gets operating system disk objects for virtual machines.

## EXAMPLES

### Example 1: Get an operating system disk by using a name
```
PS C:\>Get-WAPackVMOSDisk -Name "ContosoOSDisk"
```

This command gets an operating system disk named ContosoOSDisk.

### Example 2: Get an operating system disk by using an ID
```
PS C:\>Get-WAPackVMOSDisk -Id 66242D17-189F-480D-87CF-8E1D749998C8
```

This command gets the operating system disk that has the specified ID.

### Example 3: Get all operating system disks
```
PS C:\>Get-WAPackVMOSDisk
```

This command gets all operating system disks.

## PARAMETERS

### -ID
Specifies the unique ID of an operating system disk.

```yaml
Type: Guid
Parameter Sets: FromId
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of an operating system disk.

```yaml
Type: String
Parameter Sets: FromName
Aliases: 

Required: False
Position: 1
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

[Get-WAPackVM](.\Get-WAPackVM.md)

