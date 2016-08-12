---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# New-WAPackQuickVM
## SYNOPSIS
Creates a virtual machine based on a template.

## SYNTAX

```
New-WAPackQuickVM -Name <String> -Template <VMTemplate> -VMCredential <PSCredential>
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
For the updated topics, see  Azure WAPack Cmdletshttp://msdn.microsoft.com/library/dn776450.aspx.
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type (get-module azure).version.

The New-WAPackQuickVM cmdlet creates a virtual machine based on a template.

## EXAMPLES

### Example 1: Create a virtual machine based on a template
```
PS C:\>$Credentials = Get-Credential
PS C:\> $TemplateId = Get-WAPackVMTemplate -Id 66242D17-189F-480D-87CF-8E1D749998C8
PS C:\> New-WAPackQuickVM -Name "VirtualMachine023" -Template $TemplateId -VMCredential $Credentials
```

The first command creates a PSCredential object, and then stores it in the $Credentials variable.
The cmdlet prompts you for an account and password.
For more information, type Get-Help Get-Credential.

The second command gets a template by using the Get-WAPackVMTemplate cmdlet.
The command specifies the ID of a template.
The command stores the template object in the $TemplateID variable.

The final command creates a virtual machine named VirtualMachine023.
The command bases the virtual machine on the template stored in $TemplateId.

## PARAMETERS

### -Name
Specifies a name for the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Template
Specifies a template.
The cmdlet creates a virtual machine based on the template that you specify.
To obtain a template object, use the Get-WAPackVMTemplate cmdlet.

```yaml
Type: VMTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMCredential
Specifies the credential for the local Administrator account.
To obtain a PSCredential object, use the Get-Credential cmdlet.
For more information, type Get-Help Get-Credential.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-WAPackVM](1f74deb4-e9b0-4aeb-8e13-b1554a4ebbec)

[Get-WAPackVMTemplate](1b16012f-1da0-42f0-8407-1601cf4168e8)

