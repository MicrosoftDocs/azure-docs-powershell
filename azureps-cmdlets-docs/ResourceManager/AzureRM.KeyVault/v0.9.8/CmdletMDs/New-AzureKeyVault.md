---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=522255
schema: 2.0.0
---

# New-AzureKeyVault

## SYNOPSIS
Creates an Azure Key Vault instance.

## SYNTAX

```
New-AzureKeyVault [-VaultName] <String> [-ResourceGroupName] <String> [-Location] <String>
 [-EnabledForDeployment] [-Sku <String>] [-Tag <Hashtable[]>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureKeyVault** cmdlet creates an Azure Key Vault instance in the specified resource group.
This cmdlet also grants permissions to the currently logged on user to add, remove, or list keys and secrets in the vault.

## EXAMPLES

### Example 1: Create a Standard key vault
```
PS C:\>New-AzureKeyVault -VaultName "Contoso03Vault" -ResourceGroupName "Group14" -Location "East US"
```

This command creates a key vault named Contoso03Vault, in the Azure region East US.
The command adds the key vault to the resource group named Group14.
Because the command does not specify a value for the *SKU* parameter, it creates a Standard key vault.

### Example 2: Create a Premium key vault
```
PS C:\>New-AzureKeyVault -VaultName "Contoso03Vault" -ResourceGroupName "Group14" -Location "East US" -Sku "Premium"
```

This command creates a key vault, just like the previous example.
However, it specifies a value of Premium for the *SKU* parameter to create a Premium key vault.

## PARAMETERS

### -EnabledForDeployment
Enables the Microsoft.Compute resource provider to retrieve secrets from this key vault when this key vault is referenced in resource creation, for example when creating a virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the Azure region in which to create the key vault.
Use the command **Get-AzureLocation** to see your choices.
For more information, type `Get-Help Get-AzureLocation`.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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
Specifies the name of an existing resource group in which to create the key vault.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Specifies the SKU of the key vault instance.
For information about which features are available for each SKU, see the Azure Key Vault Pricinghttp://go.microsoft.com/fwlink/?linkid=512521 website (http://go.microsoft.com/fwlink/?linkid=512521).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: standard, premium

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies a hash table that represents resource tags.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VaultName
Specifies the name of the key vault to create.
The name can be any combination of letters, digits, or hyphens.
The name must start and end with a letter or digit.
The name must be universally unique.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### String, Guid, Switch, Hash table

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSVault

## NOTES

## RELATED LINKS

[Get-AzureKeyVault](.\Get-AzureKeyVault.md)

[Remove-AzureKeyVault](.\Remove-AzureKeyVault.md)

