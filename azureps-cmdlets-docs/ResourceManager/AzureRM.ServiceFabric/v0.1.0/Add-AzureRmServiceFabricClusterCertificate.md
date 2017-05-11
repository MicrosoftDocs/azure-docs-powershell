---
external help file: Microsoft.Azure.Commands.ServiceFabric.dll-Help.xml
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Add-AzureRmServiceFabricClusterCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Add-AzureRmServiceFabricClusterCertificate.md
<<<<<<< HEAD
gitcommit: https://github.com/Azure/azure-powershell/blob/5d5311bad38bc57d0768a327dcbfba8bfc400794
=======
gitcommit: https://github.com/Azure/azure-powershell/blob/928c918a88f76273c14645e599fb59baea0cb3d6
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
---

# Add-AzureRmServiceFabricClusterCertificate

## SYNOPSIS
<<<<<<< HEAD
Add a secondary cluster certificate to the cluster  
=======
Add a secondary cluster certificate to the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## SYNTAX

### ByExistingKeyVault
```
Add-AzureRmServiceFabricClusterCertificate [-ResourceGroupName] <String> [-Name] <String>
 -SecretIdentifier <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNewPfxAndVaultName
```
Add-AzureRmServiceFabricClusterCertificate [-ResourceGroupName] <String> [-Name] <String>
 [-KeyVaultResouceGroupName <String>] [-KeyVaultName <String>] [-CertificateOutputFolder <String>]
 [-CertificatePassword <SecureString>] -CertificateSubjectName <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByExistingPfxAndVaultName
```
Add-AzureRmServiceFabricClusterCertificate [-ResourceGroupName] <String> [-Name] <String>
 [-KeyVaultResouceGroupName <String>] [-KeyVaultName <String>] -CertificateFile <String>
 [-CertificatePassword <SecureString>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
<<<<<<< HEAD
User **Add-AzureRmServiceFabricClusterCertificate** to add a secondary cluster certificate, either from existing Azure key vault 
or creating an new Azure key vault using existing certificate provided or from an new self signed certificate created 
=======
Use **Add-AzureRmServiceFabricClusterCertificate** to add a secondary cluster certificate, either from an existing Azure key vault or creating a new Azure key vault using an existing certificate provided or from a new self-signed certificate created. 
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
It will override the secondary cluster if there is any.

## EXAMPLES

### Example 1
```
Add-AzureRmServiceFabricClusterCertificate -ResourceGroupName 'Group1' -Name 'Contoso01SFCluster' 
-SecretIdentifier 'https://contoso03vault.vault.azure.net/secrets/contoso03vaultrg/7f7de9131c034172b9df37ccc549524f'
```

<<<<<<< HEAD
This command will add a certificate in the existing Azure key vault as secondary cluster certificate
=======
This command will add a certificate in the existing Azure key vault as a secondary cluster certificate.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

### Example 2
```
PS c:\> $pwd = ConvertTo-SecureString -String "123" -AsPlainText -Force
PS c:\> add-AzureRmServiceFabricClusterCertificate -ResourceGroupName 'Group2' -Name 'Contoso02SFCluster'  -CertificateSubjectName 'Contoso.com' 
-CertificateOutputFolder 'c:\test' -CertificatePassword $pwd
```

<<<<<<< HEAD
This command will create a self signed certificate in Azure key vault, and upgrade the cluster to use it as secondary cluster certificate
=======
This command will create a self-signed certificate in the Azure key vault and upgrade the cluster to use it as a secondary cluster certificate.
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
The folder of the new certificate to be created
=======
The folder of the new certificate to be created.
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
The password of the certificate file
=======
The password of the certificate file.
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
Specifies the name of the resource group.

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
The existing Azure key vault secret Url
=======
The existing Azure key vault secret Url.
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

### Microsoft.Azure.Commands.ServiceFabric.Models.PsCluster

## NOTES

## RELATED LINKS

[Remove-AzureRmServiceFabricClusterCertificate](./Remove-AzureRmServiceFabricClusterCertificate.md)
<<<<<<< HEAD
[New-AzureRmServiceFabricCluster](./New-AzureRmServiceFabricCluster.md)
=======

[New-AzureRmServiceFabricCluster](./New-AzureRmServiceFabricCluster.md)

>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
[Add-AzureRmServiceFabricApplicationCertificate](./Add-AzureRmServiceFabricApplicationCertificate.md)
