---
external help file: Az.DataBox-help.xml
Module Name: Az.DataBox
online version: https://learn.microsoft.com/powershell/module/Az.DataBox/new-AzDataBoxKeyEncryptionKeyObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/DataBox/help/New-AzDataBoxKeyEncryptionKeyObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/DataBox/help/New-AzDataBoxKeyEncryptionKeyObject.md
---

# New-AzDataBoxKeyEncryptionKeyObject

## SYNOPSIS
Create an in-memory object for KeyEncryptionKey.

## SYNTAX

```
New-AzDataBoxKeyEncryptionKeyObject -KekType <KekType> [-IdentityProperty <IIdentityProperties>]
 [-KekUrl <String>] [-KekVaultResourceId <String>] [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for KeyEncryptionKey.

## EXAMPLES

### Example 1: Create a in-memory object for KeyEncryptionKey
```powershell
New-AzDataBoxKeyEncryptionKeyObject -KekType "CustomerManaged" -IdentityProperty @{Type = "UserAssigned"; UserAssignedResourceId = "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName"} -KekUrl "keyIdentifier" -KekVaultResourceId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName"
```

```output
KekType         KekUrl                                           KekVaultResourceId
-------         ------                                           ------------------
CustomerManaged keyIdentifier /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName
```

Create a in-memory object for KeyEncryptionKey

## PARAMETERS

### -IdentityProperty
Managed identity properties used for key encryption.
To construct, see NOTES section for IDENTITYPROPERTY properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20250201.IIdentityProperties
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KekType
Type of encryption key used for key encryption.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.KekType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KekUrl
Key encryption key.
It is required in case of Customer managed KekType.

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

### -KekVaultResourceId
Kek vault resource id.
It is required in case of Customer managed KekType.

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

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20250201.KeyEncryptionKey

## NOTES

## RELATED LINKS
