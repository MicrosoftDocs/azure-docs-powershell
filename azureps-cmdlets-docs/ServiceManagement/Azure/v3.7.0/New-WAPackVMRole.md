---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 6617AA59-CDD1-4BA9-84A7-F3914BF1D4B7
online version: 
schema: 2.0.0
---

# New-WAPackVMRole

## SYNOPSIS
Creates a virtual machine role.

## SYNTAX

### QuickCreate (Default)
```
New-WAPackVMRole -Name <String> -Label <String> -ResourceDefinition <VMRoleResourceDefinition>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromCloudService
```
New-WAPackVMRole -Name <String> -Label <String> -ResourceDefinition <VMRoleResourceDefinition>
 -CloudService <CloudService> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
For the updated topics, see [Azure WAPack Cmdlets](http://msdn.microsoft.com/library/dn776450.aspx) (http://msdn.microsoft.com/library/dn776450.aspx).
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **New-WAPackVMRole** cmdlet creates a virtual machine role.

## EXAMPLES

### Example 1: Create a virtual machine role (emulating WAP behavior)
```
PS C:\> New-WAPackVMRole -Name "ContosoVMRole01" -Label "ContosoVMRoleLabel01" -ResourceDefinition $resdef
```

Since we do not specify any cloud service (emulating WAP behavior), the command will create a cloud service for us which will have the same name as the virtual machine role.
In this case, the following command will create a virtual machine role with the name ContosoVMRole01, label ContosoVMRoleLabel01.
Note that the resource definition being used here has to be manually created though PowerShell.

## PARAMETERS

### -CloudService
Specifies a cloud service for the virtual machine role.

```yaml
Type: CloudService
Parameter Sets: FromCloudService
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Specifies a label for the virtual machine role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the virtual machine role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ResourceDefinition
Specifies a resource definition for the virtual machine role.

```yaml
Type: VMRoleResourceDefinition
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-WAPackVMRole](./Get-WAPackVMRole.md)

[Remove-WAPackVMRole](./Remove-WAPackVMRole.md)

[Set-WAPackVMRole](./Set-WAPackVMRole.md)


