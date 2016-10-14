---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
online version: .\New-AzureAutomationCredential.md
schema: 2.0.0
---

# Get-AzureAutomationCredential

## SYNOPSIS
Gets Automation credentials.

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationCredential [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByName
```
Get-AzureAutomationCredential [-Name] <String> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureAutomationCredential** cmdlet gets one or more Azure Automation credentials.
By default, all credentials are returned.
Specify the name of a credential to get a specific credential.

For security purposes, this cmdlet does not return credential passwords.

## EXAMPLES

### Example 1: Get all credentials
```
PS C:\>Get-AzureAutomationCredential -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17"
```

This command gets metadata on all credentials in the Automation account named Contoso17.

### Example 2: Get a credential
```
PS C:\>Get-AzureAutomationCredential -ResourceGroupName "MyResourceGroup" -AutomationAccountName "Contoso17" -Name "MyCredential"
```

This command gets metadata on the credential named MyCredential.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet retrieves credentials.

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

### -Name
Specifies the name of a credential to retrieve.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 2
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
The resource group name.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.CredentialInfo

## NOTES

## RELATED LINKS

[New-AzureAutomationCredential](.\New-AzureAutomationCredential.md)

[Set-AzureAutomationCredential](.\Set-AzureAutomationCredential.md)

[Remove-AzureAutomationCredential](.\Remove-AzureAutomationCredential.md)

