---
external help file: Az.ServiceLinker-help.xml
Module Name: Az.ServiceLinker
online version: https://learn.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkersystemassignedidentityauthinfoobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/ServiceLinker/help/New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/ServiceLinker/help/New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject.md
cmdletStatus: preview
cmdletStatusMessage: This cmdlet is part of a **Preview** module. Preview versions aren't recommended for use in production environments. For more information, see https://aka.ms/azps-refstatus.
---
# New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject

## SYNOPSIS
Create an in-memory object for SystemAssignedIdentityAuthInfo.

## SYNTAX

```
New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject [-Role <String[]>] [-UserName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for SystemAssignedIdentityAuthInfo.

## EXAMPLES

### Example 1: Create linker's auth info with system assigned identity
```powershell
New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject
```

```output
AuthType
--------
systemAssignedIdentity
```

Create linker's auth info with system assigned identity

## PARAMETERS

### -Role
Optional, this value specifies the Azure role to be assigned.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Username created in the database which is mapped to a user in AAD.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.SystemAssignedIdentityAuthInfo

## NOTES

## RELATED LINKS

