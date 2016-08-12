---
external help file: RMAzure_Automation.xml
online version: 7e2d3105-ae14-40c6-a715-57d63c178cde
schema: 2.0.0
---

# Set-AzureRMAutomationCertificate
## SYNOPSIS
Modifies the configuration of an Automation certificate.

## SYNTAX

```
Set-AzureRMAutomationCertificate [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-Name] <String> [-Description <String>] [-Exportable <Boolean]>] [-Password <SecureString>] [-Path <String>]
```

## DESCRIPTION
The **Set-AzureRmAutomationCertificate** cmdlet modifies the configuration of a certificate in azure_2 Automation.

## EXAMPLES

### Example 1: Modify a certificate
```
PS C:\>$Password = ConvertTo-SecureString -String "Password" -AsPlainText -Force
PS C:\> Set-AzureAutomationCertificate -AutomationAccountName "Contos17" -Name "ContosoCertificate" -Path "./cert.pfx" -Password $Password -ResourceGroupName "ResourceGroup01"
```

The first command converts a plain text password to be a secure string by using the ConvertTo-SecureString cmdlet.
The command stores that object in the $Password variable.

The second command modifies a certificate named ContosoCertificate.
The command uses the password stored in $Password.
The command specifies the account name and the path of the file that it uploads.

## PARAMETERS

### -AutomationAccountName
Specifies the name of the Automation account for which this cmdlet modifies a certificate.

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
Specifies a description for the certificate that this cmdlet modifies.

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
Type: Boolean]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the certificate that this cmdlet modifies.

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
Specifies the path to a script file to upload.
The file can be a .cer file or a .pfx file.

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

### -ResourceGroupName
Specifies the name of the resource group for which this cmdlet modifies a certificate.

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

[New-AzureRmAutomationCertificate](4316d596-2954-42e8-905f-840853dab7d5)

[Remove-AzureRmAutomationCertificate](1ed3a0d7-541d-4a07-b0d6-4538f98450f7)

