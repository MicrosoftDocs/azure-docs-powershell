---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 78C3E089-848D-40F6-83EB-F3D0ADA6C934
---

# Get-AzureSiteRecoveryVault

## SYNOPSIS
Gets Site Recovery vaults from the current subscription.

## SYNTAX

### Default (Default)
```
Get-AzureSiteRecoveryVault [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByName
```
Get-AzureSiteRecoveryVault -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryVault** cmdlet gets a list of Azure Site Recovery vaults or a specific Site Recovery vault from the current subscription.

## EXAMPLES

### Example 1: Get the active vault
```
PS C:\> Get-AzureSiteRecoveryVault

Name             : ContosoVault
ID               : 6467459117394545458
CloudServiceName : CS-West-US-RecoveryServices
SubscriptionId   : a5aa5997-33e5-46cc-8ab8-b8d89b76b7ba
StatusReason     : 
Status           : Active
Location         : West US
```

This command gets the active Azure Site Recovery vault.

## PARAMETERS

### -Name
Specifies the name of the vault to get.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureSiteRecoveryVault](./New-AzureSiteRecoveryVault.md)


