---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=522257
schema: 2.0.0
---

# Set-AzureKeyVaultAccessPolicy

## SYNOPSIS
Grants or modifies existing permissions for a user or application to perform operations with the Azure Key Vault.

## SYNTAX

### ByServicePrincipalName
```
Set-AzureKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>]
 -ServicePrincipalName <String> [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>]
 [-EnabledForDeployment] [-PassThru] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByUserPrincipalName
```
Set-AzureKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] -UserPrincipalName <String>
 [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>] [-EnabledForDeployment] [-PassThru]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByObjectId
```
Set-AzureKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] -ObjectId <Guid>
 [-ApplicationId <Guid>] [-PermissionsToKeys <String[]>] [-PermissionsToSecrets <String[]>]
 [-EnabledForDeployment] [-PassThru] [-Profile <AzureProfile>] [<CommonParameters>]
```

### None
```
Set-AzureKeyVaultAccessPolicy [-VaultName] <String> [[-ResourceGroupName] <String>] [-EnabledForDeployment]
 [-PassThru] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureKeyVaultAccessPolicy** cmdlet grants or modifies existing permissions for a user or application to perform the specified operations with the Azure Key Vault.
It does not modify the permissions that other users or applications have on the key vault.

The following directories must all be the same Azure directory: 

- The Azure directory in which the key vault owner's user account resides. 
- The default directory of the Azure subscription in which the key vault resides. 
- The Azure directory in which the application service principal is registered.

Examples of scenarios when these conditions are not met and this cmdlet will not work are: 

- Authorizing a user from a different organization to manage your key vault.
Each organization has its own directory. 
- Your Azure account has multiple directories.
If you register an application in a directory other than the default directory, you will not be able to authorize that application to use your key vaults.
The application must be in the default directory.

Note that although specifying the resource group is optional for this cmdlet, you should do so for better performance.

## EXAMPLES

### Example 1: Grant permissions to a user for a key vault and modify the permissions
```
PS C:\>Set-AzureKeyVaultAccessPolicy -VaultName "Contoso03Vault" -UserPrincipalName "PattiFuller@contoso.com" -PermissionsToKeys create,import,delete,list -PermissionsToSecrets set,delete
PS C:\> Set-AzureKeyVaultAccessPolicy -VaultName "Contoso03Vault" -UserPrincipalName "PattiFuller@contoso.com" -PermissionsToSecrets set,delete,get -PassThru
PS C:\> Set-AzureKeyVaultAccessPolicy -VaultName "Contoso03Vault" -UserPrincipalName "PattiFuller@contoso.com" -PermissionsToKeys @() -PassThru
```

The first command grants permissions for a user in your Azure Active Directory, PattiFuller@contoso.com, to perform operations on keys and secrets with a key vault named Contoso03Vault.

The second command modifies the permissions that were granted to PattiFuller@contoso.com in the first command, to now allow getting secrets in addition to setting and deleting them.
The permissions to key operations remain unchanged after this command.
The *PassThru* parameter results in the updated key vault object being returned by the cmdlet.

The final command further modifies the existing permissions for PattiFuller@contoso.com to remove all permissions to key operations.
The permissions to secret operations remain unchanged after this command.
The *PassThru* parameter results in the updated key vault object being returned by the cmdlet.

### Example 2: Grant permissions for an application service principal to read and write secrets
```
PS C:\>Set-AzureKeyVaultAccessPolicy -VaultName "Contoso03Vault" -ServicePrincipalName "http://payroll.contoso.com" -PermissionsToSecrets "get,set"
```

This command grants permissions for an application for a vault named Contoso03Vault.
The *ServicePrincipalName* parameter specifies the application.
The application must be registered in your Azure Active Directory.
The value of the *ServicePrincipalName* parameter must be either the service principal name of the application or the application ID GUID.
This example specifies the service principal name http://payroll.contoso.com, and the command grants the application permissions to read and write secrets.

### Example 3: Grant permissions for an application using its object ID
```
PS C:\>Set-AzureKeyVaultAccessPolicy -VaultName "Contoso03Vault" -ObjectId 34595082-9346-41b6-8d6b-295a2808b8db -PermissionsToSecrets "get,set"
```

This command grants the application permissions to read and write secrets.
This example specifies the application using the object ID of the service principal of the application.

### Example 4: Enable secrets to be retrieved from a vault by the Microsoft.Compute resource provider
```
PS C:\>Set-AzureKeyVaultAccessPolicy -VaultName "Contoso03Vault" -ResourceGroupName "Group14" -EnabledForDeployment
```

This command grants the permissions for secrets to be retrieved from the Contoso03Vault vault by the Microsoft.Compute resource provider.

## PARAMETERS

### -EnabledForDeployment
Enables the Microsoft.Compute resource provider to retrieve secrets from this key vault when this key vault is referenced in resource creation, for example when creating a virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: ByServicePrincipalName, ByUserPrincipalName, ByObjectId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: None
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Specifies the object ID of the user or service principal in Azure Active Directory for which to grant permissions.

```yaml
Type: Guid
Parameter Sets: ByObjectId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the updated key vault object.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PermissionsToKeys
Specifies an array of key operation permissions to grant to a user or service principal.
The acceptable values for this parameter are:

- Decrypt
- Encrypt
- UnwrapKey
- WrapKey
- Verify 
- Sign
- Get
- List
- Update
- Create
- Import
- Delete 
- Backup 
- Restore
- All

```yaml
Type: String[]
Parameter Sets: ByServicePrincipalName, ByUserPrincipalName, ByObjectId
Aliases: 
Accepted values: decrypt, encrypt, unwrapKey, wrapKey, verify, sign, get, list, update, create, import, delete, backup, restore, all

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PermissionsToSecrets
Specifies an array of secret operation permissions to grant to a user or service principal.
The acceptable values for this parameter are:

- Get
- List
- Set
- Delete 
- All

```yaml
Type: String[]
Parameter Sets: ByServicePrincipalName, ByUserPrincipalName, ByObjectId
Aliases: 
Accepted values: get, list, set, delete, all

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group associated with the key vault whose access policy is being modified.
If not specified, this cmdlet searches for the key vault in the current subscription.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePrincipalName
Specifies the service principal name of the application to which to grant permissions.
Specify the application ID, also known as client ID, registered for the application in Azure Active Directory.
The application with the service principal name that this parameter specifies must be registered in the Azure directory that contains your current subscription or the subscription specified by the *SubscriptionName* parameter, if that parameter is specified.

```yaml
Type: String
Parameter Sets: ByServicePrincipalName
Aliases: SPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserPrincipalName
Specifies the user principal name of the user to whom to grant permissions.
This user principal name must exist in the directory associated with the current subscription or in the subscription specified by the *SubscriptionName* parameter, if that parameter is specified.

```yaml
Type: String
Parameter Sets: ByUserPrincipalName
Aliases: UPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Specifies the name of a key vault.
This cmdlet modifies the access policy for the key vault that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationId
Specifies the ID of application that a user must use to grant permissions.```yaml
Type: Guid
Parameter Sets: ByObjectId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String, Guid, String[], Switch

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSVault

## NOTES

## RELATED LINKS

[Remove-AzureKeyVaultAccessPolicy](.\Remove-AzureKeyVaultAccessPolicy.md)

