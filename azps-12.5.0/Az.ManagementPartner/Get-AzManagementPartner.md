---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ManagementPartner.dll-Help.xml
Module Name: Az.ManagementPartner
online version: https://learn.microsoft.com/powershell/module/az.managementpartner/get-azmanagementpartner
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagementPartner/ManagementPartner/help/Get-AzManagementPartner.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagementPartner/ManagementPartner/help/Get-AzManagementPartner.md
---

# Get-AzManagementPartner

## SYNOPSIS
Gets the Microsoft Partner Network(MPN) ID of the current authenticated user or service principal.

## SYNTAX

```
Get-AzManagementPartner [[-PartnerId] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Gets the Microsoft Partner Network(MPN) ID of the current authenticated user or service principal.

## EXAMPLES

### Example 1
```powershell
Get-AzManagementPartner
```

```output
PartnerId   : 4977985
PartnerName : Test_Test_DPORTest
TenantId    : aaaabbbb-0000-cccc-1111-dddd2222eeee
ObjectId    : ffffffff-eeee-dddd-cccc-bbbbbbbbbbb0
State       : Active
```

Get the current management partner id

### Example 2
```powershell
Get-AzManagementPartner -PartnerId 4977985
```

```output
PartnerId   : 4977985
PartnerName : Test_Test_DPORTest
TenantId    : aaaabbbb-0000-cccc-1111-dddd2222eeee
ObjectId    : ffffffff-eeee-dddd-cccc-bbbbbbbbbbb0
State       : Active
```

Get the current management partner id using a partner id, if they don't match, it will fail

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PartnerId
The management partner id, it is a 6 digits number

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.ManagementPartner.PSManagementPartner

## NOTES

## RELATED LINKS

[Remove-AzManagementPartner](./Remove-AzManagementPartner.md)

[New-AzManagementPartner](./New-AzManagementPartner.md)

[Update-AzManagementPartner](./Update-AzManagementPartner.md)
