---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 656BE930-E778-40B0-8A75-BFE52DE386CE
online version: https://learn.microsoft.com/en-us/powershell/module/az.compute/add-azvmsssecret
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVmssSecret.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVmssSecret.md
---

# Add-AzVmssSecret

## SYNOPSIS
Adds a secret to a VMSS.

## SYNTAX

```
Add-AzVmssSecret [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-SourceVaultId] <String>]
 [[-VaultCertificate] <VaultCertificate[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzVmssSecret** cmdlet adds a secret to the Virtual Machine Scale Set (VMSS).
The secret must be stored in an Azure Key Vault.
For more information relating to Key Vault, see [What is Azure Key Vault?](/azure/key-vault/general/overview).
For more information about the cmdlets, see [Azure Key Vault Cmdlets](/powershell/module/az.keyvault) or the [Set-AzKeyVaultSecret](/powershell/module/az.keyvault/set-azkeyvaultsecret) cmdlet.

## EXAMPLES

### Example 1: Add a secret to the VMSS
```
PS C:\> $Vault = Get-AzKeyVault -VaultName "ContosoVault"
PS C:\> $CertConfig = New-AzVmssVaultCertificateConfig -CertificateUrl "http://keyVaultName.vault.contoso.net/secrets/secretName/secretVersion" -CertificateStore "Certificates"
PS C:\> $VMSS = New-AzVmssConfig
PS C:\> Add-AzVmssSecret -VirtualMachineScaleSet $VMSS -SourceVaultId $Vault.ResourceId -VaultCertificate $CertConfig
```

This example adds a secret to the VMSS.
The first command uses the Get-AzKeyVault cmdlet to get a vault secret from the vault named ContosoVault and stores the result in the variable named $Vault.
The second command uses the **New-AzVmssVaultCertificateConfig** cmdlet to create a Key Vault certificate configuration using the specified certificate URL from the certificate store named Certificates and stores the results in the variable named $CertConfig.
The third command uses the **New-AzVmssConfig** cmdlet to create a VMSS configuration object and stores the result in the variable named $VMSS.
The fourth command adds a secret to the VMSS using the vault secret using the key resource ID and the vault certificate stored in the $Vault and $CertConfig variables.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceVaultId
Specifies the resource ID of the Key Vault that contains the certificates that you can add to the virtual machine.
This value also acts as the key for adding multiple certificates.
This means that you can use the same value for the *SourceVaultId* parameter when you add multiple certificates from the same Key Vault.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultCertificate
Specifies the Vault **Certificate** object that contains the certificate URL and certificate name.
You can use the [New-AzVmssVaultCertificateConfig](./New-AzVmssVaultCertificateConfig.md) cmdlet to create this object.

```yaml
Type: VaultCertificate[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Specifies the VMSS object.
You can use the [New-AzVmssConfig](./New-AzVmssConfig.md) cmdlet to create this object.

```yaml
Type: PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### VirtualMachineScaleSet
Parameter 'VirtualMachineScaleSet' accepts value of type 'VirtualMachineScaleSet' from the pipeline

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[New-AzVmssVaultCertificateConfig](./New-AzVmssVaultCertificateConfig.md)

[New-AzVmssConfig](./New-AzVmssConfig.md)
