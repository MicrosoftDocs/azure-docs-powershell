---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Move-AzureNetworkSecurityGroup.md
schema: 2.0.0
---

# Move-AzureService

## SYNOPSIS
Migrates a cloud service to the Azure Resource Manager stack.

## SYNTAX

### AbortMigrationParameterSet
```
Move-AzureService [-Abort] [-ServiceName] <String> [-DeploymentName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### CommitMigrationParameterSet
```
Move-AzureService [-Commit] [-ServiceName] <String> [-DeploymentName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### PrepareNewMigrationParameterSet
```
Move-AzureService [-Prepare] [-ServiceName] <String> [-DeploymentName] <String> [-CreateNewVirtualNetwork]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### PrepareExistingMigrationParameterSet
```
Move-AzureService [-Prepare] [-ServiceName] <String> [-DeploymentName] <String> [-UseExistingVirtualNetwork]
 [-VirtualNetworkResourceGroupName] <String> [-VirtualNetworkName] <String> [-SubnetName] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### ValidateExistingMigrationParameterSet
```
Move-AzureService [-Validate] [-ServiceName] <String> [-DeploymentName] <String> [-UseExistingVirtualNetwork]
 [-VirtualNetworkResourceGroupName] <String> [-VirtualNetworkName] <String> [-SubnetName] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### ValidateNewMigrationParameterSet
```
Move-AzureService [-Validate] [-ServiceName] <String> [-DeploymentName] <String> [-CreateNewVirtualNetwork]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Move-AzureService** cmdlet migrates a cloud service and a deployment inside that service to a resource group in the Azure Resource Manager stack.

## EXAMPLES

### Example 1: Prepare service migration
```
PS C:\>Move-AzureService -Prepare -ServiceName "ContosoService" -DeploymentName "ContosoVM" -CreateNewVirtualNetwork
```

This command prepares the service named ContosoService for migration to the Azure Resource Manager stack.
The migration includes the deployment named ContosoVM.

### Example 2: Start service migration
```
PS C:\>Move-AzureService -Commit -ServiceName "ContosoService" -DeploymentName "ContosoVM"
```

This command starts migration of the service named ContosoService to the Azure Resource Manager stack.
The migration includes the deployment named ContosoVM.

### Example 3: Cancel service migration
```
PS C:\>Move-AzureService -Abort -ServiceName "ContosoService" -DeploymentName "ContosoVM"
```

This command cancels migration of the service named ContosoService to the Azure Resource Manager stack.

### Example 4: Prepare service migration to an existing virtual network
```
PS C:\>Move-AzureService -Prepare -ServiceName "ContosoService" -DeploymentName "ContosoVM" -UseExistingVirtualNetwork -VirtualNetworkResourceGroupName "VnetRG" -VirtualNetworkName "ContosoVNET" -SubnetName "ContosoSubnet"
```

This command prepares the service named ContosoService for migration to the Azure Resource Manager stack.
The migration includes the deployment named ContosoVM.
The migration uses a virtual network that was previously created.

### Example 5: Validate service migration
```
PS C:\>Move-AzureService -Validate -ServiceName "ContosoService" -DeploymentName "ContosoVM" -CreateNewVirtualNetwork
```

This command validates migration for the service named ContosoService to the Azure Resource Manager stack.
The migration includes the deployment named ContosoVM.

### Example 6: Validate service migration to an existing virtual network
```
PS C:\>Move-AzureService -Validate -ServiceName "contosoService" -DeploymentName "contosoVM" -UseExistingVirtualNetwork -VirtualNetworkResourceGroupName "vnetRG" -VirtualNetworkName "contosoVNET" -SubnetName "contosoSubnet"
```

This command validates migration for the service named ContosoService to the Azure Resource Manager stack.
The migration includes the deployment named ContosoVM.
The migration uses a virtual network that was previously created.

## PARAMETERS

### -Abort
Indicates that this cmdlet cancels the service migration.

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

### -ServiceName
Specifies the name of the cloud service that this cmdlet migrates.

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

### -DeploymentName
Specifies the name of the cloud service deployment that this cmdlet migrates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -Commit
Indicates that this cmdlet starts the service migration.

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
Indicates that this cmdlet prepares the cloud service for migration.

```yaml
Type: SwitchParameter
Parameter Sets: PrepareNewMigrationParameterSet, PrepareExistingMigrationParameterSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateNewVirtualNetwork
Indicates that this cmdlet creates a virtual network in the Azure Resource Manager stack.

```yaml
Type: SwitchParameter
Parameter Sets: PrepareNewMigrationParameterSet, ValidateNewMigrationParameterSet
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseExistingVirtualNetwork
Indicates that this cmdlet migrates the cloud service to an existing virtual network in the Azure Resource Manager stack.

```yaml
Type: SwitchParameter
Parameter Sets: PrepareExistingMigrationParameterSet, ValidateExistingMigrationParameterSet
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkResourceGroupName
Specifies the name of the resource group of an existing virtual network.

```yaml
Type: String
Parameter Sets: PrepareExistingMigrationParameterSet, ValidateExistingMigrationParameterSet
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Specifies the name of a virtual network.

```yaml
Type: String
Parameter Sets: PrepareExistingMigrationParameterSet, ValidateExistingMigrationParameterSet
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Specifies the name of the Subnet inside the virtual network.

```yaml
Type: String
Parameter Sets: PrepareExistingMigrationParameterSet, ValidateExistingMigrationParameterSet
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Validate
Specifies that this cmdlet validates the cloud service for migration.

```yaml
Type: SwitchParameter
Parameter Sets: ValidateExistingMigrationParameterSet, ValidateNewMigrationParameterSet
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

[Move-AzureStorageAccount](.\Move-AzureStorageAccount.md)

[Move-AzureVirtualNetwork](.\Move-AzureVirtualNetwork.md)

