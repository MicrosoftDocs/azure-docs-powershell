---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmADApplication

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### ApplicationWithoutCredentialParameterSet (Default)
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]>
 [<CommonParameters>]
```

### ApplicationWithPasswordPlainParameterSet
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]> -Password <String>
 [-StartDate <DateTime>] [-EndDate <DateTime>] [<CommonParameters>]
```

### ApplicationWithPasswordCredentialParameterSet
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]>
 -PasswordCredentials <PSADPasswordCredential[]> [<CommonParameters>]
```

### ApplicationWithKeyPlainParameterSet
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]> -KeyValue <String>
 [-KeyType <String>] [-KeyUsage <String>] [-StartDate <DateTime>] [-EndDate <DateTime>] [<CommonParameters>]
```

### ApplicationWithKeyCredentialParameterSet
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]>
 -KeyCredentials <PSADKeyCredential[]> [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -DisplayName
The display name for the application.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndDate
The end date till which password or key is valid.
Default value is one year after current time.

```yaml
Type: DateTime
Parameter Sets: ApplicationWithPasswordPlainParameterSet, ApplicationWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HomePage
The URL to the application's homepage.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentifierUris
The URIs that identify the application.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyCredentials
The collection of key credentials associated with the application.

```yaml
Type: PSADKeyCredential[]
Parameter Sets: ApplicationWithKeyCredentialParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyType
The type of the key credentials associated with the application.
Acceptable values are 'AsymmetricX509Cert', 'Password' and 'Symmetric'.
Default is 'AsymmetricX509Cert'

```yaml
Type: String
Parameter Sets: ApplicationWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyUsage
The usage of the key credentials associated with the application.
Acceptable values are 'Sign' and 'Verify'.
Default is 'Verify'

```yaml
Type: String
Parameter Sets: ApplicationWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyValue
The value for the key credentials associated with the application that will be valid for one year by default.

```yaml
Type: String
Parameter Sets: ApplicationWithKeyPlainParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
The value for the password credential associated with the application that will be valid for one year by default.

```yaml
Type: String
Parameter Sets: ApplicationWithPasswordPlainParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PasswordCredentials
The collection of password credentials associated with the application.

```yaml
Type: PSADPasswordCredential[]
Parameter Sets: ApplicationWithPasswordCredentialParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDate
The start date after which password or key would be valid.
Default value is current time.

```yaml
Type: DateTime
Parameter Sets: ApplicationWithPasswordPlainParameterSet, ApplicationWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
System.String[]
Microsoft.Azure.Commands.Resources.Models.ActiveDirectory.PSADPasswordCredential[]
Microsoft.Azure.Commands.Resources.Models.ActiveDirectory.PSADKeyCredential[]
System.DateTime

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.ActiveDirectory.PSADApplication

## NOTES

## RELATED LINKS

