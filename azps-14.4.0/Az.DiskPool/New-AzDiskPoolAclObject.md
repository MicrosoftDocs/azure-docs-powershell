---
external help file: Az.DiskPool-help.xml
Module Name: Az.DiskPool
online version: https://learn.microsoft.com/powershell/module/Az.DiskPool/new-azdiskpoolaclobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/DiskPool/help/New-AzDiskPoolAclObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/DiskPool/help/New-AzDiskPoolAclObject.md
cmdletStatus: preview
cmdletStatusMessage: This cmdlet is part of a **Preview** module. Preview versions aren't recommended for use in production environments. For more information, see https://aka.ms/azps-refstatus.
---

# New-AzDiskPoolAclObject

## SYNOPSIS
Create an in-memory object for Acl.

## SYNTAX

```
New-AzDiskPoolAclObject -InitiatorIqn <String> -MappedLun <String[]>
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for Acl.

## EXAMPLES

### Example 1: Create an acl object
```powershell
New-AzDiskPoolAclObject -InitiatorIqn 'iqn.2021-05.com.microsoft:target0' -MappedLun @('lun0')
```

```output
InitiatorIqn                      MappedLun
------------                      ---------
iqn.2021-05.com.microsoft:target0 {lun0}
```

This command creates an acl object.

## PARAMETERS

### -InitiatorIqn
iSCSI initiator IQN (iSCSI Qualified Name); example: "iqn.2005-03.org.iscsi:client".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MappedLun
List of LUN names mapped to the ACL.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.Acl

## NOTES

## RELATED LINKS
