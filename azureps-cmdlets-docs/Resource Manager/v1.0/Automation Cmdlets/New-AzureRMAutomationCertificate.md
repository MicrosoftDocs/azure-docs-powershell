---
external help file: RMAzure_Automation.xml
online version: 7e2d3105-ae14-40c6-a715-57d63c178cde
schema: 2.0.0
---

# New-AzureRMAutomationCertificate
## SYNOPSIS
Creates an Automation certificate.

## SYNTAX

```
New-AzureRMAutomationCertificate [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Path] <String> [-Description <String>] [-Exportable] [-Password <SecureString>]
```

## DESCRIPTION
The **New-AzureRmAutomationCertificate** cmdlet creates a certificate in azure_2 Automation.
Provide the path to a certificate file to upload.

## EXAMPLES

### Example 1: Create a new certificate
```
PS C:\>$Password = ConvertTo-SecureString -String "Password" -AsPlainText -Force
PS C:\> New-AzureRmAutomationCertificate -AutomationAccountName "Contoso17" -Name "ContosoCertificate" -Path "./cert.pfx" -Password $Password -ResourceGroupName "ResourceGroup01"
```

The first command converts a plain text password to be a secure string by using the ConvertTo-SecureString cmdlet.
The command stores that object in the $Password variable.

The second command creates a certificate named ContosoCertificate.
The command uses the password stored in $Password.
The command specifies the account name and the path of the file that it uploads.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet stores the certificate.

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
Specifies a description for the certificate.

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

### -Exportable
Specifies whether the certificate can be exported.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name for the certificate.

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

### -Password
Specifies the password for the certificate file.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path to a script file that this cmdlet uploads.
The file can be a .cer or a .pfx file.

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
Specifies the name of the resource group for which this cmdlet creates a certificate.

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

### Microsoft.Azure.Commands.Automation.Model.CertificateInfo

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationCertificate](7e2d3105-ae14-40c6-a715-57d63c178cde)

[Remove-AzureRmAutomationCertificate](1ed3a0d7-541d-4a07-b0d6-4538f98450f7)

[Set-AzureRmAutomationCertificate](77502783-0006-4288-917f-26f265ccfcbe)

