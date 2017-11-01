---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureRmAccount

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### User (Default)
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] [-Credential <PSCredential>]
 [-TenantId <String>] [<CommonParameters>]
```

### ServicePrincipal
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] -Credential <PSCredential>
 [-ServicePrincipal] -TenantId <String> [-SubscriptionId <String>] [-SubscriptionName <String>]
 [<CommonParameters>]
```

### SubscriptionId
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [-ApplicationId <String>] [-TenantId <String>] [-AccessToken <String>]
 [-AccountId <String>] [-SubscriptionId <String>] [<CommonParameters>]
```

### SubscriptionName
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] [-Credential <PSCredential>]
 [-CertificateThumbprint <String>] [-ApplicationId <String>] [-TenantId <String>] [-AccessToken <String>]
 [-AccountId <String>] [-SubscriptionName <String>] [<CommonParameters>]
```

### ServicePrincipalCertificate
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>]
 -CertificateThumbprint <String> -ApplicationId <String> [-ServicePrincipal] -TenantId <String>
 [<CommonParameters>]
```

### AccessToken
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] [-TenantId <String>]
 -AccessToken <String> -AccountId <String> [<CommonParameters>]
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

### -AccessToken
AccessToken

```yaml
Type: String
Parameter Sets: SubscriptionId, SubscriptionName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: AccessToken
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountId
Account Id for access token

```yaml
Type: String
Parameter Sets: SubscriptionId, SubscriptionName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: AccessToken
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationId
SPN

```yaml
Type: String
Parameter Sets: SubscriptionId, SubscriptionName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ServicePrincipalCertificate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint
Certificate Hash (Thumbprint)

```yaml
Type: String
Parameter Sets: SubscriptionId, SubscriptionName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ServicePrincipalCertificate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Optional credential

```yaml
Type: PSCredential
Parameter Sets: User, SubscriptionId, SubscriptionName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: PSCredential
Parameter Sets: ServicePrincipal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Environment
Environment containing the account to log into

```yaml
Type: AzureEnvironment
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnvironmentName
Name of the environment containing the account to log into

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipal
{{Fill ServicePrincipal Description}}

```yaml
Type: SwitchParameter
Parameter Sets: ServicePrincipal, ServicePrincipalCertificate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Subscription

```yaml
Type: String
Parameter Sets: ServicePrincipal, SubscriptionId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionName
Subscription Name

```yaml
Type: String
Parameter Sets: ServicePrincipal, SubscriptionName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantId
Optional tenant name or ID

```yaml
Type: String
Parameter Sets: User, SubscriptionId, SubscriptionName, AccessToken
Aliases: Domain

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ServicePrincipal, ServicePrincipalCertificate
Aliases: Domain

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSAzureProfile

## NOTES

## RELATED LINKS

