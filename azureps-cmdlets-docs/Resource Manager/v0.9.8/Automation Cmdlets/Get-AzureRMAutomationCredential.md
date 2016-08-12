---
external help file: RMAzure_Automation.xml
online version: 2e0b5b0e-df2b-4747-bb42-8e6b94f397e0
schema: 2.0.0
---

# Get-AzureRMAutomationCredential
## SYNOPSIS
Gets Automation credentials.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureRMAutomationCredential [-ResourceGroupName] <String> [-AutomationAccountName] <String>
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureRMAutomationCredential [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String>
```

## DESCRIPTION
The **Get-AzureRmAutomationCredential** cmdlet gets one or more azure_2 Automation credentials.
By default, all credentials are returned.
Specify the name of a credential to get a specific credential.

For security purposes, this cmdlet does not return credential passwords.

## EXAMPLES

### Example 1: Get all credentials
```
PS C:\>Get-AzureRmAutomationCredential -ResourceGroupName "ResourceGroup01" -AutomationAccountName "Contoso17"
```

This command gets metadata for all credentials in the Automation account named Contoso17.

### Example 2: Get a credential
```
PS C:\>Get-AzureRmAutomationCredential -ResourceGroupName "ResourceGroup01" -AutomationAccountName "Contoso17" -Name "ContosoCredential"
```

This command gets metadata for the credential named ContosoCredential in the Automation account named Contoso17.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet retrieves credentials.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a credential to retrieve.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the resource group for which this cmdlet retrieves credentials.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.CredentialInfo

## NOTES

## RELATED LINKS

[New-AzureRmAutomationCredential](2e0b5b0e-df2b-4747-bb42-8e6b94f397e0)

[Remove-AzureRmAutomationCredential](6a171b2b-1fdc-4642-a3d5-495b39fa7cff)

[Set-AzureRmAutomationCredential](f0f039fd-2b0b-4993-8408-471e0f7ad10b)

