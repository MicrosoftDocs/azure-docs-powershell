---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://learn.microsoft.com/powershell/module/az.keyvault/new-azkeyvaultmanagedhsm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/New-AzKeyVaultManagedHsm.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/New-AzKeyVaultManagedHsm.md
---

# New-AzKeyVaultManagedHsm

## SYNOPSIS
Creates a managed HSM.

## SYNTAX

```
New-AzKeyVaultManagedHsm [-Name] <String> [-ResourceGroupName] <String> [-Location] <String>
 [-Administrator] <String[]> [-Sku <String>] -SoftDeleteRetentionInDays <Int32> [-PublicNetworkAccess <String>]
 [-EnablePurgeProtection] [-UserAssignedIdentity <String[]>] [-Tag <Hashtable>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [-SubscriptionId <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzKeyVaultManagedHsm** cmdlet creates a managed HSM in the specified resource group. To add, 
remove, or list keys in the managed HSM, user should: 
1. grant permissions by adding user ID to Administrator;
2. add role assignment for user like "Managed HSM Crypto User" and so on;
3. back up security domain data of a managed HSM using `Export-AzKeyVaultSecurityDomain`.

## EXAMPLES

### Example 1: Create a StandardB1 managed HSM
```powershell
New-AzKeyVaultManagedHsm -Name 'myhsm' -ResourceGroupName 'myrg1' -Location 'eastus2euap' -Administrator "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -SoftDeleteRetentionInDays 70
```

```output
Name  Resource Group Name Location    SKU
----  ------------------- --------    ---
myhsm myrg1               eastus2euap StandardB1
```

This command creates a managed HSM named myhsm in the location eastus2euap. The command
adds the managed HSM to the resource group named myrg1. Because the command does not specify a
value for the *SKU* parameter, it creates a Standard_B1 managed HSM.

### Example 2: Create a CustomB32 managed HSM
```powershell
New-AzKeyVaultManagedHsm -Name 'myhsm' -ResourceGroupName 'myrg1' -Location 'eastus2euap' -Administrator "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Sku 'CustomB32' -SoftDeleteRetentionInDays 70
```

```output
Name  Resource Group Name Location    SKU

----  ------------------- --------    ---
myhsm myrg1               eastus2euap CustomB32
```

This command creates a managed HSM, just like the previous example. However, it specifies a value of
CustomB32 for the *SKU* parameter to create a CustomB32 managed HSM.

### Example 3: Create a managed HSM with an user assigned identity
```powershell
New-AzKeyVaultManagedHsm -Name 'myhsm' -ResourceGroupName 'myrg1' -Location 'eastus2euap' -Administrator "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"-SoftDeleteRetentionInDays 70 -UserAssignedIdentity /subscriptions/xxxx/resourceGroups/xxxx/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName | Format-List
```

```output
Managed HSM Name                        : myhsm
Resource Group Name                     : myrg1
Location                                : eastus2euap
Resource ID                             : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/bez-rg/pro
                                          viders/Microsoft.KeyVault/managedHSMs/bezmhsm
HSM Pool URI                            :
Tenant ID                               : aaaabbbb-0000-cccc-1111-dddd2222eeee
Initial Admin Object Ids                : {xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}
SKU                                     : StandardB1
Soft Delete Enabled?                    : True
Enabled Purge Protection?               : False
Soft Delete Retention Period (days)     : 70
Public Network Access                   : Enabled
IdentityType                            : UserAssigned
UserAssignedIdentities                  : /subscriptions/xxxx/resourceGroups/xxxx/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName
Provisioning State                      : Succeeded
Status Message                          : The Managed HSM is provisioned and ready to use.
Security Domain ActivationStatus        : Active
Security Domain ActivationStatusMessage : Your HSM has been activated and can be used for cryptographic operations.
Regions                                 : 
Tags
```

This command creates a managed HSM with an user assigned identity.

## PARAMETERS

### -Administrator
Initial administrator object id for this managed HSM pool.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Run cmdlet in the background

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -EnablePurgeProtection
specifying whether protection against purge is enabled for this managed HSM pool. The setting is effective only if soft delete is also enabled. Enabling this functionality is irreversible.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the Azure region in which to create the key vault.
Use the command Get-AzResourceProvider with the ProviderNamespace parameter to see your choices.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name of the managed HSM to create.
The name can be any combination of letters, digits, or hyphens.
The name must start and end with a letter or digit.
The name must be universally unique.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HsmName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicNetworkAccess
Controls permission for data plane traffic coming from public networks while private endpoint is enabled.

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

### -ResourceGroupName
Specifies the name of an existing resource group in which to create the key vault.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Specifies the SKU of the managed HSM instance.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SoftDeleteRetentionInDays
Specifies how long the deleted managed hsm pool is retained, and how long until the managed hsm pool in the deleted state can be purged.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The ID of the subscription.
By default, cmdlets are executed in the subscription that is set in the current context. If the user specifies another subscription, the current cmdlet is executed in the subscription specified by the user.
Overriding subscriptions only take effect during the lifecycle of the current cmdlet. It does not change the subscription in the context, and does not affect subsequent cmdlets.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
A hash table which represents resource tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserAssignedIdentity
The set of user assigned identities associated with the managed HSM. Its value will be ARM resource ids in the form: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/userAssignedIdentities/{identityName}'.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSManagedHsm

## NOTES

## RELATED LINKS

[Get-AzKeyVaultManagedHsm](./Get-AzKeyVaultManagedHsm.md)

[Remove-AzKeyVaultManagedHsm](./Remove-AzKeyVaultManagedHsm.md)

[Update-AzKeyVaultManagedHsm](./Update-AzKeyVaultManagedHsm.md)

[Undo-AzKeyVaultManagedHsmRemoval](./Undo-AzKeyVaultManagedHsmRemoval.md)
