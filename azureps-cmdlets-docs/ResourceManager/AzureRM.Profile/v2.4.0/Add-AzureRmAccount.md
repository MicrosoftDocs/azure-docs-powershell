---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
ms.assetid: 0F557076-3AC6-408E-B389-A4D6CF0CAE39
online version: 
schema: 2.0.0
---

# Add-AzureRmAccount

## SYNOPSIS
Adds an authenticated account to use for Resource Manager cmdlet requests.

## SYNTAX

### UserWithSubscriptionId (Default)
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] [-Credential <PSCredential>]
 [-TenantId <String>] [-SubscriptionId <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServicePrincipalWithSubscriptionName
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] -Credential <PSCredential>
 [-ServicePrincipal] -TenantId <String> -SubscriptionName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServicePrincipalWithSubscriptionId
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] -Credential <PSCredential>
 [-ServicePrincipal] -TenantId <String> [-SubscriptionId <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserWithSubscriptionName
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] [-Credential <PSCredential>]
 [-TenantId <String>] -SubscriptionName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServicePrincipalCertificateWithSubscriptionId
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>]
 -CertificateThumbprint <String> -ApplicationId <String> [-ServicePrincipal] -TenantId <String>
 [-SubscriptionId <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ServicePrincipalCertificateWithSubscriptionName
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>]
 -CertificateThumbprint <String> -ApplicationId <String> [-ServicePrincipal] -TenantId <String>
 -SubscriptionName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AccessTokenWithSubscriptionId
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] [-TenantId <String>]
 -AccessToken <String> -AccountId <String> [-SubscriptionId <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AccessTokenWithSubscriptionName
```
Add-AzureRmAccount [-Environment <AzureEnvironment>] [-EnvironmentName <String>] [-TenantId <String>]
 -AccessToken <String> -AccountId <String> -SubscriptionName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureRmAccount** cmdlet adds an authenticated Azure account to use for Azure Resource Manager cmdlet requests.

You can use this authenticated account only with Resource Manager cmdlets.
To add an authenticated account for use with Service Management cmdlets, use the Add-AzureAccount or the Import-AzurePublishSettingsFile cmdlet.

## EXAMPLES

### Example 1: Add an account that requires interactive logon
```
PS C:\>Add-AzureRmAccount
Account: pfuller@contoso.com
Environment: AzureCloud
Subscription: xxxx-xxxx-xxxx-xxxx
Tenant: xxxx-xxxx-xxxx-xxxx
```

This command adds an Azure Resource Manager account.

To run Resource Manager cmdlets by using this account, you must provide Microsoft account or organizational ID credentials at the prompt.
If multi-factor authentication is enabled for your credentials, you must log on by using the interactive option or use service principal authentication.

### Example 2: Add an account that authenticates by using organizational ID credentials
```
PS C:\>$Credential = Get-Credential
PS C:\> Add-AzureRmAccount -Credential $Credential
Account: pfuller@contoso.com
Environment: AzureChinaCloud
Subscription: xxxx-xxxx-xxxx-xxxx
Tenant: xxxx-xxxx-xxxx-xxxx
```

The first command gets the user credentials, and then stores them in the $Credential variable.

The second command adds a Resource Manager account that has the credentials in $Credential.

This account authenticates with Resource Manager using organizational ID credentials.
You cannot use multi-factor authentication or Microsoft account credentials to run Resource Manager cmdlets by using this account.

### Example3: Add an account that authenticates by using service principal credentials
```
PS C:\>$Credential = Get-Credential
PS C:\> Add-AzureRmAccount -Credential $Credential -Tenant 'xxxx-xxxx-xxxx-xxxx' -ServicePrincipal
Account: xxxx-xxxx-xxxx-xxxx
Environment: AzureCloud
Subscription: yyyy-yyyy-yyyy-yyyy
Tenant: xxxx-xxxx-xxxx-xxxx
```

The first command gets the user credentials, and then stores them in the $Credential variable.

The second command adds a Resource Manager account that has the credentials stored in $Credential for the specified Tenant.
The *ServicePrincipal* parameter indicates that the account authenticates as a service principal.

### Example 4: Add an account for a specific tenant and subscription
```
PS C:\>Add-AzureRmAccount -Tenant 'xxxx-xxxx-xxxx-xxxx' -SubscriptionId 'yyyy-yyyy-yyyy-yyyy'
Account: pfuller@contoso.com
Environment: AzureCloud
Subscription: yyyy-yyyy-yyyy-yyyy
Tenant: xxxx-xxxx-xxxx-xxxx
```

This command adds a Resource Manager account to run cmdlets for the specified tenant and subscription.
By default, the session uses the account.

## PARAMETERS

### -AccessToken
Specifies an access token.

```yaml
Type: String
Parameter Sets: AccessTokenWithSubscriptionId, AccessTokenWithSubscriptionName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountId
Specifies the ID of an authenticated account that run Resource Manager cmdlets.

```yaml
Type: String
Parameter Sets: AccessTokenWithSubscriptionId, AccessTokenWithSubscriptionName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationId
Specifies an application ID.

```yaml
Type: String
Parameter Sets: ServicePrincipalCertificateWithSubscriptionId, ServicePrincipalCertificateWithSubscriptionName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint
Specifies the thumbprint of a certificate.

```yaml
Type: String
Parameter Sets: ServicePrincipalCertificateWithSubscriptionId, ServicePrincipalCertificateWithSubscriptionName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object.
For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

The **PSCredential** object provides the user ID and password for organizational ID credentials, or the application ID and secret for service principal credentials.

```yaml
Type: PSCredential
Parameter Sets: UserWithSubscriptionId, UserWithSubscriptionName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: PSCredential
Parameter Sets: ServicePrincipalWithSubscriptionName, ServicePrincipalWithSubscriptionId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Environment
Specifies the Azure environment.
Valid values are: AzureCloud and AzureChinaCloud.
The default is AzureCloud.

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
Specifies the name of the environment.

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
Indicates that this account authenticates by providing service principal credentials.

```yaml
Type: SwitchParameter
Parameter Sets: ServicePrincipalWithSubscriptionName, ServicePrincipalWithSubscriptionId, ServicePrincipalCertificateWithSubscriptionId, ServicePrincipalCertificateWithSubscriptionName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Specifies the ID of the subscription.
If you do not specify this parameter, this cmdlet uses the first subscription from the subscription list.

```yaml
Type: String
Parameter Sets: UserWithSubscriptionId, ServicePrincipalWithSubscriptionId, ServicePrincipalCertificateWithSubscriptionId, AccessTokenWithSubscriptionId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SubscriptionName
Specifies the name of the subscription.

```yaml
Type: String
Parameter Sets: ServicePrincipalWithSubscriptionName, UserWithSubscriptionName, ServicePrincipalCertificateWithSubscriptionName, AccessTokenWithSubscriptionName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TenantId
Specifies the ID of the tenant.

```yaml
Type: String
Parameter Sets: UserWithSubscriptionId, UserWithSubscriptionName, AccessTokenWithSubscriptionId, AccessTokenWithSubscriptionName
Aliases: Domain

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ServicePrincipalWithSubscriptionName, ServicePrincipalWithSubscriptionId, ServicePrincipalCertificateWithSubscriptionId, ServicePrincipalCertificateWithSubscriptionName
Aliases: Domain

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

