---
external help file: RMAzure_Automation.xml
online version: ea09d4b6-ff25-4b91-b957-328222844689
schema: 2.0.0
---

# New-AzureRMAutomationCredential
## SYNOPSIS
Creates an Automation credential.

## SYNTAX

```
New-AzureRMAutomationCredential [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Value] <PSCredential> [-Description <String>]
```

## DESCRIPTION
The **New-AzureRmAutomationCredential** cmdlet creates a credential as a **PSCredential** object in azure_2 Automation.

## EXAMPLES

### Example 1: Create a credential
```
PS C:\>$User = "Contoso\PFuller"
PS C:\> $Password = ConvertTo-SecureString "Password" -AsPlainText -Force
PS C:\> $Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $Password
PS C:\> New-AzureRmAutomationCredential -AutomationAccountName "Contoso17" -Name "ContosoCredential" -Value $Credential -ResourceGroupName "ResourceGroup01"
```

The first command assigns a user name to the $User variable.

The second command converts a plain text password into a secure string by using the ConvertTo-SecureString cmdlet.
The command stores that object in the $Password variable.

The third command creates a credential based on $User and $Password, and then stores it in the $Credential variable.

The final command creates an Automation credential named ContosoCredential that uses $Credential.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account in which this cmdlet stores the credential.

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
Specifies a description for the credential.

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
Specifies a name for the credential.

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
Specifies a description for the resource group for which this cmdlet creates a credential.

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

Required: True
Position: 4
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

[Remove-AzureRmAutomationCredential](6a171b2b-1fdc-4642-a3d5-495b39fa7cff)

[Set-AzureRmAutomationCredential](f0f039fd-2b0b-4993-8408-471e0f7ad10b)

