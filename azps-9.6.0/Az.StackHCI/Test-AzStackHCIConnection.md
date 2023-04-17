---
external help file: 
Module Name: Az.StackHCI
online version: https://learn.microsoft.com/powershell/module/az.stackhci/test-azstackhciconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Test-AzStackHCIConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Test-AzStackHCIConnection.md
---

# Test-AzStackHCIConnection

## SYNOPSIS
Test-AzStackHCIConnection verifies connectivity from on-premises clustered nodes to the Azure services required by Azure Stack HCI.

Note: Test-AzStackhHCIConnection is deprecated.
Please use 'Invoke-AzStackHciConnectivityValidation' from 'AzStackHCI.EnvironmentChecker' module for enhanced connectivity verification tests.
For more information, see https://learn.microsoft.com/en-us/azure-stack/hci/whats-new#new-azure-stack-hci-environment-checker-tool.

## SYNTAX

```
Test-AzStackHCIConnection [[-EnvironmentName] <String>] [[-Region] <String>] [[-ComputerName] <String>]
 [[-Credential] <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
Test-AzStackHCIConnection verifies connectivity from on-premises clustered nodes to the Azure services required by Azure Stack HCI.

Note: Test-AzStackhHCIConnection is deprecated.
Please use 'Invoke-AzStackHciConnectivityValidation' from 'AzStackHCI.EnvironmentChecker' module for enhanced connectivity verification tests.
For more information, see https://learn.microsoft.com/en-us/azure-stack/hci/whats-new#new-azure-stack-hci-environment-checker-tool.

## EXAMPLES

### Example 1: 
```powershell
Test-AzStackHCIConnection
```

```output
Test: Connect to Azure Stack HCI Service
EndpointTested: https://azurestackhci-df.azurefd.net/health
IsRequired: True
Result: Succeeded
```

Invoking on one of the cluster node.
Success case.

### Example 2:
```powershell
Test-AzStackHCIConnection
```

```output
Test: Connect to Azure Stack HCI Service
EndpointTested: https://azurestackhci-df.azurefd.net/health
IsRequired: True
Result: Failed
FailedNodes: Node1inClus2, Node2inClus3
```

Invoking on one of the cluster node.
Failed case.

## PARAMETERS

### -ComputerName
Specifies one of the cluster node in on-premise cluster that is being registered to Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credential for the ComputerName.
Default is the current user executing the Cmdlet.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnvironmentName
Specifies the Azure Environment.
Default is AzureCloud.
Valid values are AzureCloud, AzureChinaCloud, AzurePPE, AzureCanary, AzureUSGovernment

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Region
Specifies the Region to connect to.
Not used unless it is Canary region.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject. Returns following Properties in PSCustomObject
Test: Name of the test performed.
EndpointTested: Endpoint used in the test.
IsRequired: True or False
Result: Succeeded or Failed
FailedNodes: List of nodes on which the test failed.

## NOTES

ALIASES

## RELATED LINKS
