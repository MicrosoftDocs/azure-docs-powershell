---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureStorageAccount.md
schema: 2.0.0
---

# Set-AzureStorageAccount

## SYNOPSIS
Updates the properties of a storage account in an Azure subscription.

## SYNTAX

### GeoReplicationEnabled (Default)
```
Set-AzureStorageAccount [-StorageAccountName] <String> [-Label <String>] [-Description <String>]
 [-GeoReplicationEnabled <Boolean>] [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

### AccountType
```
Set-AzureStorageAccount [-StorageAccountName] <String> [-Label <String>] [-Description <String>]
 [-Type <String>] [-Profile <AzureProfile>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureStorageAccount** cmdlet updates the properties of an Azure storage account in the current subscription.
Properties that can be set are: **Label**, **Description**, **Type** and **GeoReplicationEnabled**.

## EXAMPLES

### Example 1: Update the label for a storage account
```
PS C:\>Set-AzureStorageAccount -StorageAccountName "ContosoStorage01" -Label "ContosoAccnt" -Description "Contoso storage account"
```

This command updates the **Label** and **Description** properties for the storage account named ContosoStorage01.

### Example 2: Enable geo-replication for a storage account
```
PS C:\>Set-AzureStorageAccount -StorageAccountName "ContosoStorage01" -GeoReplicationEnabled $False
```

This command sets the **GeoReplicationEnabled** property to $False for the storage account named ContosoStorage01.

### Example 3: Disable geo-replication for a storage account
```
PS C:\>Set-AzureStorageAccount -StorageAccountName "ContosoStorage01" -GeoReplicationEnabled $True
```

This command sets the **GeoReplicationEnabled** property to $True for the storage account named ContosoStorage01.

## PARAMETERS

### -StorageAccountName
Specifies the name of the storage account that this cmdlet modifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Label
Specifies a label for the storage account.
The label may be up to 100 characters long.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the storage account.
The description may be up to 1024 characters long.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GeoReplicationEnabled
Specifies whether the storage account is created with the geo-replication enabled.

```yaml
Type: Boolean
Parameter Sets: GeoReplicationEnabled
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type of the storage account.
Valid values are: 

- Standard_LRS
- Standard_ZRS
- Standard_GRS
- Standard_RAGRS
- Premium_LRS

If this parameter is not specified, the default value is Standard_GRS.

The effect of specifying the *GeoReplicationEnabled* parameter is the same as specifying Standard_GRS in the *Type* parameter.

Standard_ZRS or Premium_LRS accounts cannot be changed to other account types, and vice versa.

```yaml
Type: String
Parameter Sets: AccountType
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Not Specified```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageAccount](.\Get-AzureStorageAccount.md)

[New-AzureStorageAccount](.\New-AzureStorageAccount.md)

[Remove-AzureStorageAccount](.\Remove-AzureStorageAccount.md)

