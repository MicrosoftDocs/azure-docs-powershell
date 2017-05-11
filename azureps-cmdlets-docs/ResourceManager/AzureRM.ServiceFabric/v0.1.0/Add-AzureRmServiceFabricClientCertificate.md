---
external help file: Microsoft.Azure.Commands.ServiceFabric.dll-Help.xml
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Add-AzureRmServiceFabricClientCertificate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ServiceFabric/Commands.ServiceFabric/help/Add-AzureRmServiceFabricClientCertificate.md
<<<<<<< HEAD
gitcommit: https://github.com/Azure/azure-powershell/blob/caac14a8d00d1a4768dbfef7746a272147172c1e
=======
gitcommit: https://github.com/Azure/azure-powershell/blob/928c918a88f76273c14645e599fb59baea0cb3d6
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
---

# Add-AzureRmServiceFabricClientCertificate

## SYNOPSIS
Add common name or thumbprint to the cluster for client authentication purposes.

## SYNTAX

### SingleUpdateWithThumbprint
```
Add-AzureRmServiceFabricClientCertificate [-Admin] [-ResourceGroupName] <String> [-Name] <String>
 -Thumbprint <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SingleUpdateWithCommonName
```
Add-AzureRmServiceFabricClientCertificate [-Admin] [-ResourceGroupName] <String> [-Name] <String>
 -CommonName <String> -IssuerThumbprint <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MultipleUpdatesWithCommonName
```
Add-AzureRmServiceFabricClientCertificate [-ResourceGroupName] <String> [-Name] <String>
 -ClientCertificateCommonName <PSClientCertificateCommonName[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MultipleUpdatesWithThumbprint
```
Add-AzureRmServiceFabricClientCertificate [-ResourceGroupName] <String> [-Name] <String>
 [-AdminClientThumbprint <String[]>] [-ReadonlyClientThumbprint <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
<<<<<<< HEAD
Use **Add-AzureRmServiceFabricClientCertificate** to add a common name and issuer thumbprint or certificate thumbprint to the cluster, 
so that the client can use it for authentication
=======
Use **Add-AzureRmServiceFabricClientCertificate** to add a common name and issuer thumbprint or certificate thumbprint to the cluster, so the client can use it for authentication.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## EXAMPLES

### Example 1
```
PS c:> Add-AzureRmServiceFabricClientCertificate -ResourceGroupName 'Group1' -Name 'Contoso01SFCluster' -Thumbprint 5F3660C715EBBDA31DB1FFDCF508302348DE8E7A -IsAdmin
```

<<<<<<< HEAD
This command will add the certificate with thumbprint '5F3660C715EBBDA31DB1FFDCF508302348DE8E7A' to the cluster, so the client use the certificate as admin to communicate with the cluster
=======
This command will add the certificate with thumbprint '5F3660C715EBBDA31DB1FFDCF508302348DE8E7A' to the cluster, so the client can use the certificate as admin to communicate with the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

### Example 2
```
PS c:> Add-AzureRmServiceFabricClientCertificate -ResourceGroupName 'Group2' -Name 'Contoso02SFCluster' -CommonName 'Contoso.com' -IssuerThumbprint 5F3660C715EBBDA31DB1FFDCF508302348DE8E7A
```

<<<<<<< HEAD
This command will add a read only client certificate which's common name is 'Contoso.com' and issuer thumbprint is '5F3660C715EBBDA31DB1FFDCF508302348DE8E7A' to the cluster
=======
This command will add a read only client certificate that's common name is 'Contoso.com' and issuer thumbprint is '5F3660C715EBBDA31DB1FFDCF508302348DE8E7A' to the cluster.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

## PARAMETERS

### -Admin
<<<<<<< HEAD
Client authentication type
=======
Client authentication type.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: SwitchParameter
Parameter Sets: SingleUpdateWithThumbprint, SingleUpdateWithCommonName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AdminClientThumbprint
<<<<<<< HEAD
Specify client certificate thumbprint which only has admin permission
=======
Specify client certificate thumbprint that only has admin permission.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String[]
Parameter Sets: MultipleUpdatesWithThumbprint
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClientCertificateCommonName
<<<<<<< HEAD
Specify client common name , issuer thumbprint and authentication type
=======
Specify client common name, issuer thumbprint, and authentication type.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: PSClientCertificateCommonName[]
Parameter Sets: MultipleUpdatesWithCommonName
Aliases: CertCommonName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CommonName
<<<<<<< HEAD
Specify client certificate common name
=======
Specify client certificate common name.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: SingleUpdateWithCommonName
Aliases: 

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

### -IssuerThumbprint
Specify client certificate issuer thumbprint
=======
### -IssuerThumbprint
Specify client certificate issuer thumbprint.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: SingleUpdateWithCommonName
Aliases: 

Required: True
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

### -ReadonlyClientThumbprint
<<<<<<< HEAD
Specify client certificate thumbprint which only has read only permission
=======
Specify client certificate thumbprint that has read only permission.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String[]
Parameter Sets: MultipleUpdatesWithThumbprint
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Thumbprint
<<<<<<< HEAD
Specify client certificate thumbprint
=======
Specify client certificate thumbprint.
>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e

```yaml
Type: String
Parameter Sets: SingleUpdateWithThumbprint
Aliases: ClientCertificateThumbprint

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

### System.Collections.Hashtable
System.String
<<<<<<< HEAD
=======

>>>>>>> 5ea771e45c43745a1a9149d7b45047392135567e
System.Boolean

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PsCluster

## NOTES

## RELATED LINKS

[Remove-AzureRmServiceFabricClientCertificate](./Remove-AzureRmServiceFabricClientCertificate.md)
