---
external help file: RMAzure_Automation.xml
online version: ea09d4b6-ff25-4b91-b957-328222844689
schema: 2.0.0
---

# Set-AzureRMAutomationCredential
## SYNOPSIS
Modifies an Automation credential.

## SYNTAX

```
Set-AzureRMAutomationCredential [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Description <String>] [-Value <PSCredential>]
```

## DESCRIPTION
The **Set-AzureRmAutomationCredential** cmdlet modifies a credential as a **PSCredential** object in azure_2 Automation.

## EXAMPLES

### Example 1: Update a credential
```
PS C:\>$User = "Contoso\DChew"
PS C:\> $Password = ConvertTo-SecureString "Password" -AsPlainText -Force
PS C:\> $Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $Password
PS C:\> Set-AzureRmAutomationCredential -AutomationAccountName "Contoso17" -Name "ContosoCredential" -ResourceGroupName "ResourceGroup01" -Value $Credential
```

The first command assigns a user name to the $User variable.

The second command converts a plain text password into a secure string by using the ConvertTo-SecureString cmdlet.
The command stores that object in the $Password variable.

The third command creates a credential based on $User and $Password, and then stores it in the $Credential variable.

The final command modifies the Automation credential named ContosoCredential to use the credential in $Credential.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet modifies a credential.

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

### -Description
Specifies a description for the credential that this cmdlet modifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the credential that this cmdlet modifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet modifies a credential.

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

### -Value
Specifies the credentials as a **PSCredential** object.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.CredentialInfo

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationCredential](ea09d4b6-ff25-4b91-b957-328222844689)

[New-AzureRmAutomationCredential](2e0b5b0e-df2b-4747-bb42-8e6b94f397e0)

[Remove-AzureRmAutomationCredential](6a171b2b-1fdc-4642-a3d5-495b39fa7cff)

