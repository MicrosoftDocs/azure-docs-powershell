---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Move-AzureNetworkSecurityGroup.md
schema: 2.0.0
---

# Move-AzureStorageAccount

## SYNOPSIS
Migrates a storage account to the Azure Resource Manager stack.

## SYNTAX

### ValidateMigrationParameterSet
```
Move-AzureStorageAccount [-Validate] [-StorageAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### AbortMigrationParameterSet
```
Move-AzureStorageAccount [-Abort] [-StorageAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### CommitMigrationParameterSet
```
Move-AzureStorageAccount [-Commit] [-StorageAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### PrepareMigrationParameterSet
```
Move-AzureStorageAccount [-Prepare] [-StorageAccountName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Move-AzureStorageAccount** cmdlet migrates a storage account to a resource group in the Azure Resource Manager stack.

## EXAMPLES

### Example 1: Prepare storage account migration
```
PS C:\>Move-AzureStorageAccount -Prepare -StorageAccountName "ContosoStorageName"
```

This command prepares the storage account named ContosoStorageName for migration to the Azure Resource Manager stack.

### Example 2: Start storage account migration
```
PS C:\>Move-AzureStorageAccount -Commit -StorageAccountName "ContosoStorageName"
```

This command starts migration of the storage account named ContosoStorageName to the Azure Resource Manager stack.

### Example 3: Validate storage account migration
```
PS C:\>Move-AzureStorageAccount -Validate -StorageAccountName "ContosoStorageName"
```

This command validates migration for the storage account named ContosoStorageName to the Azure Resource Manager stack.

## PARAMETERS

### -Validate
Specifies that this cmdlet validates the storage account for migration.

```yaml
Type: SwitchParameter
Parameter Sets: ValidateMigrationParameterSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the name of the storage account that this cmdlet migrates.

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

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Abort
Indicates that this cmdlet cancels the storage account migration.

```yaml
Type: SwitchParameter
Parameter Sets: AbortMigrationParameterSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Commit
Indicates that this cmdlet starts the storage account migration.

```yaml
Type: SwitchParameter
Parameter Sets: CommitMigrationParameterSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prepare
Indicates that this cmdlet prepares the storage account for migration.

```yaml
Type: SwitchParameter
Parameter Sets: PrepareMigrationParameterSet
Aliases: 

Required: True
Position: 0
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

[Move-AzureNetworkSecurityGroup](.\Move-AzureNetworkSecurityGroup.md)

[Move-AzureReservedIP](.\Move-AzureReservedIP.md)

[Move-AzureRouteTable](.\Move-AzureRouteTable.md)

[Move-AzureService](.\Move-AzureService.md)

[Move-AzureVirtualNetwork](.\Move-AzureVirtualNetwork.md)

