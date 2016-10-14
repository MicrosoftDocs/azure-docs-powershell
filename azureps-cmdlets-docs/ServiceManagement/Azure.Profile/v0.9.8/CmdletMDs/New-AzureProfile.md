---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=397624
schema: 2.0.0
---

# New-AzureProfile

## SYNOPSIS

## SYNTAX

### Certificate
```
New-AzureProfile [-Environment <AzureEnvironment>] [-SubscriptionId] <String> [-StorageAccount <String>]
 [-Certificate] <X509Certificate2> [<CommonParameters>]
```

### Token
```
New-AzureProfile [-Environment <AzureEnvironment>] [-SubscriptionId] <String> [-StorageAccount <String>]
 [-AccessToken] <String> [-AccountId] <String> [<CommonParameters>]
```

### ServicePrincipal
```
New-AzureProfile [-Environment <AzureEnvironment>] [-SubscriptionId] <String> [-StorageAccount <String>]
 [-Credential] <PSCredential> [-Tenant] <String> [-ServicePrincipal] [<CommonParameters>]
```

### Credentials
```
New-AzureProfile [-Environment <AzureEnvironment>] [-SubscriptionId] <String> [-StorageAccount <String>]
 [-Credential] <PSCredential> [[-Tenant] <String>] [<CommonParameters>]
```

### Empty
```
New-AzureProfile [-Environment <AzureEnvironment>] [<CommonParameters>]
```

### File
```
New-AzureProfile [-Path] <String> [<CommonParameters>]
```

### PropertyBag
```
New-AzureProfile [-Properties] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### 1:
```
PS C:\>
```

## PARAMETERS

### -Environment
```yaml
Type: AzureEnvironment
Parameter Sets: Certificate, Token, ServicePrincipal, Credentials, Empty
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
```yaml
Type: String
Parameter Sets: Certificate, Token, ServicePrincipal, Credentials
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccount
```yaml
Type: String
Parameter Sets: Certificate, Token, ServicePrincipal, Credentials
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccessToken
```yaml
Type: String
Parameter Sets: Token
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountId
```yaml
Type: String
Parameter Sets: Token
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
```yaml
Type: PSCredential
Parameter Sets: ServicePrincipal, Credentials
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
```yaml
Type: String
Parameter Sets: ServicePrincipal
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Credentials
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipal
```yaml
Type: SwitchParameter
Parameter Sets: ServicePrincipal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificate
```yaml
Type: X509Certificate2
Parameter Sets: Certificate
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
```yaml
Type: String
Parameter Sets: File
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties
```yaml
Type: Hashtable
Parameter Sets: PropertyBag
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

