---
external help file: Microsoft.WindowsAzure.Commands.SqlDatabase.dll-Help.xml
online version: 29e46b74-9254-47ea-9c41-dd77a9f3b2aa
schema: 2.0.0
---

# New-AzureSqlDatabaseServerContext

## SYNOPSIS
Creates a server connection context.

## SYNTAX

### ByServerNameWithSqlAuth (Default)
```
New-AzureSqlDatabaseServerContext [-ServerName] <String> [-Credential] <PSCredential>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByServerNameWithCertAuth
```
New-AzureSqlDatabaseServerContext [-ServerName] <String> [-UseSubscription] [[-SubscriptionName] <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByManageUrlWithSqlAuth
```
New-AzureSqlDatabaseServerContext [[-ServerName] <String>] [-ManageUrl] <Uri> [-Credential] <PSCredential>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByFullyQualifiedServerNameWithCertAuth
```
New-AzureSqlDatabaseServerContext [-FullyQualifiedServerName] <String> [-UseSubscription]
 [[-SubscriptionName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByFullyQualifiedServerNameWithSqlAuth
```
New-AzureSqlDatabaseServerContext [-FullyQualifiedServerName] <String> [-Credential] <PSCredential>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSqlDatabaseServerContext** cmdlet creates an ssSDS server connection context.
Use ssNoVersion authentication to create a connection context to a nextref_database server by using the specified credentials.
You can specify the nextref_database server by name, by the fully qualified name, or by URL.
To obtain a credential, use the Get-Credential cmdlet that prompts you to specify the user name and password.

Use the **New-AzureSqlDatabaseServerContext** cmdlet with certificate based authentication to create a connection context to the specified nextref_database server by using the specified azure_2 subscription data.
You can specify nextref_database server by name or by the fully qualified name.
You can specify the subscription data as a parameter or it can be retrieved from the current azure_2 subscription.
Use the Select-AzureSubscriptionhttp://msdn.microsoft.com/library/windowsazure/jj152833.aspx cmdlet to select the current azure_2 subscription.

## EXAMPLES

### Example 1: Create a context by using SQL Server authentication
```
PS C:\>$Credential = Get-Credential
PS C:\> $Context = New-AzureSqlDatabaseServerContext -ServerName "lpqd0zbr8y" -Credential $Credential
PS C:\> $Database17 = New-AzureSqlDatabase -ConnectionContext $Context -DatabaseName "Database17" -MaxSizeGB 50 -Collation "SQL_Latin1_General_CP1_CI_AS"
```

This example uses the ssNoVersion authentication.

The first command prompts you for server administrator credentials, and stores the credentials in the $Credential variable.

The second command connects to the nextref_database server named lpqd0zbr8y by using $Credential.

The final command creates a database named Database17 on the server that is part of the context in $Context.

### Example 2: Create a context by using certificate based authentication
```
PS C:\>$SubscriptionId = <Subscription ID>
PS C:\> $Thumbprint = <Certificate Thumbprint>
PS C:\> $Certificate = Get-Item "Cert:\CurrentUser\My\$Thumbprint"
PS C:\> Set-AzureSubscription -SubscriptionName "Subscription07" -SubscriptionId $SubscriptionId -Certificate $Certificate
PS C:\> Select-AzureSubscription -SubscriptionName "Subscription07"
PS C:\> $Context = New-AzureSqlDatabaseServerContext -ServerName "lpqd0zbr8y" -UseSubscription
```

This example uses the certificate based authentication.

The first two commands assign values to the $SubscriptionId and $Thumbprint variables.

The third command gets the certificate identified by the thumbprint in $Thumbprint, and stores it in $Certificate.

The fourth command sets the subscription to be Subscription07, and the fifth command selects that subscription.

The final command creates a context in the current subscription for the server named lpqd0zbr8y.

## PARAMETERS

### -ServerName
Specifies the name of the database server.

```yaml
Type: String
Parameter Sets: ByServerNameWithSqlAuth, ByServerNameWithCertAuth
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ByManageUrlWithSqlAuth
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies a credential object that provides ssNoVersion authentication for you to access the server.

```yaml
Type: PSCredential
Parameter Sets: ByServerNameWithSqlAuth, ByManageUrlWithSqlAuth, ByFullyQualifiedServerNameWithSqlAuth
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSubscription
Indicates that this cmdlet uses azure_2 subscription for creating the connection context.

```yaml
Type: SwitchParameter
Parameter Sets: ByServerNameWithCertAuth, ByFullyQualifiedServerNameWithCertAuth
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionName
Specifies the name of the azure_2 subscription that this cmdlet uses to create the connection context.
If you do not specify a value for this parameter, the cmdlet uses the current subscription.
Run the Select-AzureSubscription cmdlet to change the current subscription.

```yaml
Type: String
Parameter Sets: ByServerNameWithCertAuth, ByFullyQualifiedServerNameWithCertAuth
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManageUrl
Specifies the URL that this cmdlet uses to access the ssSDSnextref_azportal for the server.

```yaml
Type: Uri
Parameter Sets: ByManageUrlWithSqlAuth
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedServerName
Specifies the fully qualified domain name (FQDN) name for the ssSDS server.
For example, Server02.database.windows.net.

```yaml
Type: String
Parameter Sets: ByFullyQualifiedServerNameWithCertAuth, ByFullyQualifiedServerNameWithSqlAuth
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.SqlDatabase.Services.Server.IServerDataServiceContext

## NOTES
* If you authenticate without specifying a domain, and if you use powershell 2.0, the Get-Credential cmdlet returns a backslash (\\) prepended to the username, for example, \user. powershell 3.0 does not add the backslash. This backslash is not recognized by the *Credential* parameter of the **New-AzureSqlDatabaseServerContext** cmdlet. To remove it, use commands similar to the following:

  `PS C:\\\> $Credential = Get-Credential`
`PS C:\\\> $Credential = New-Object -TypeName 'System.Management.Automation.PSCredential' -ArgumentList $Credential.Username.Replace("\",""),$Credential.Password`

## RELATED LINKS

[Azure SQL Database Cmdlets](.\Azure.SQLDatabase.md)

[Get-AzureSqlDatabase](.\Get-AzureSqlDatabase.md)

[New-AzureSqlDatabase](.\New-AzureSqlDatabase.md)

[Remove-AzureSqlDatabase](.\Remove-AzureSqlDatabase.md)

[Set-AzureSqlDatabase](.\Set-AzureSqlDatabase.md)

