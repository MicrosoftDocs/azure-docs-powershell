---
external help file: Microsoft.Azure.Commands.ServiceFabric.dll-Help.xml
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Add-AzureRmServiceFabricApplicationCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Add-AzureRmServiceFabricApplicationCertificate.md
<<<<<<< HEAD
gitcommit: https://github.com/Azure/azure-powershell/blob/caac14a8d00d1a4768dbfef7746a272147172c1e
=======
gitcommit: https://github.com/Azure/azure-powershell/blob/b59ab30cc7553989a7f5abf07d2880d6c1e7b21c
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
---

# Add-AzureRmServiceFabricApplicationCertificate

## SYNOPSIS
Add a new certificate to the Virtual Machine Scale Set(s) that make up the cluster. The certificate is intended to be used as an application certificate.

## SYNTAX

### ByExistingKeyVault
```
Add-AzureRmServiceFabricApplicationCertificate [-ResourceGroupName] <String> [-Name] <String>
 -SecretIdentifier <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNewPfxAndVaultName
```
Add-AzureRmServiceFabricApplicationCertificate [-ResourceGroupName] <String> [-Name] <String>
 [-KeyVaultResouceGroupName <String>] [-KeyVaultName <String>] [-CertificateOutputFolder <String>]
 [-CertificatePassword <SecureString>] -CertificateSubjectName <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByExistingPfxAndVaultName
```
Add-AzureRmServiceFabricApplicationCertificate [-ResourceGroupName] <String> [-Name] <String>
 [-KeyVaultResouceGroupName <String>] [-KeyVaultName <String>] -CertificateFile <String>
 [-CertificatePassword <SecureString>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
<<<<<<< HEAD
Use  **Add-AzureRmServiceFabricApplicationCertificate**  to install a certificate to all nodes in the cluster. 
You can specify a certificate you already have or have the system generate an new one for you, and upload it to an new or existing Azure key vault.
=======
Use **Add-AzureRmServiceFabricApplicationCertificate** to install a certificate to all nodes in the cluster. 
You can specify a certificate you already have or have the system generate a new one for you, and upload it to a new or existing Azure key vault.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## EXAMPLES

### Example 1
```
PS c:> Add-AzureRmServiceFabricApplicationCertificate -ResourceGroupName 'Group1' -Name 'Contoso01SFCluster' -SecretIdentifier 'https://contoso03vault.vault.azure.net/secrets/contoso03vaultrg/7f7de9131c034172b9df37ccc549524f'
```

<<<<<<< HEAD
This command will add a certificate from existing Azure key vault to all nodetypes of the cluster
=======
This command will add a certificate from existing Azure key vault to all node types of the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

### Example 2
```
PS c:\> $pwd = ConvertTo-SecureString -String '123' -AsPlainText -Force
PS C:\> Add-AzureRmServiceFabricApplicationCertificate -ResourceGroupName 'Group2' -Name 'Contoso02SFCluster' -KeyVaultName 'Contoso02Vault' -KeyVaultResouceGroupName 'Contoso02VaultRg'
        -CertificateSubjectName 'cn=Contoso.com' -CertificateOutputFolder 'c:\test' -CertificatePassword $pwd
```

<<<<<<< HEAD
This command will create self signed certificate in Azure key vault with the key vault resource group name and key vault Name, then installs to all node types of the cluster, and downloads the certificate under fold 'c:\test', the name of the certificate downloaded 
is same as the name of key vault certificate
=======
This command will create a self-signed certificate in the Azure key vault with the key vault resource group name and key vault Name, installs to all node types of the cluster, and downloads the certificate under folder 'c:\test'. The name of the certificate downloaded is same as the name of key vault certificate.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## PARAMETERS

### -CertificateFile
<<<<<<< HEAD
The existing certificate file path
=======
The existing certificate file path.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: ByExistingPfxAndVaultName
Aliases: Source

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificateOutputFolder
<<<<<<< HEAD
The folder path of the new certificate to be created
=======
The folder path of the new certificate to be created.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: ByNewPfxAndVaultName
Aliases: Destination

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificatePassword
<<<<<<< HEAD
The password of the pfx file
=======
The password of the pfx file.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: SecureString
Parameter Sets: ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: CertPassword

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CertificateSubjectName
<<<<<<< HEAD
The Dns name of the certificate to be created
=======
The Dns name of the certificate to be created.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: ByNewPfxAndVaultName
Aliases: Subject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

<<<<<<< HEAD
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

### -KeyVaultName
Azure key vault name
=======

### -KeyVaultName
Azure key vault name.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyVaultResouceGroupName
<<<<<<< HEAD
Azure key vault resource group name
=======
Azure key vault resource group name.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: ByNewPfxAndVaultName, ByExistingPfxAndVaultName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
<<<<<<< HEAD
Specify the name of the cluster
=======
Specify the name of the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specify the name of the resource group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecretIdentifier
<<<<<<< HEAD
The existing Azure key vault secret uri
=======
The existing Azure key vault secret uri.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: ByExistingKeyVault
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

<<<<<<< HEAD
=======
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

>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PSKeyVault

## NOTES

## RELATED LINKS

[Add-AzureRmServiceFabricClusterCertificate](./Add-AzureRmServiceFabricClusterCertificate.md)
<<<<<<< HEAD
[New-AzureRmServiceFabricCluster](./New-AzureRmServiceFabricCluster.md)
=======

[New-AzureRmServiceFabricCluster](./New-AzureRmServiceFabricCluster.md)
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
