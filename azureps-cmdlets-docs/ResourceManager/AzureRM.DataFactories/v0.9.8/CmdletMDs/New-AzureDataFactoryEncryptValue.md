---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
online version: 4076bd7c-248e-4f9f-b93a-7f2ffb9b0a51
schema: 2.0.0
---

# New-AzureDataFactoryEncryptValue

## SYNOPSIS
Encrypts sensitive data (e.g.
password, SQL Server connection string) and returns an encrypted value.

## SYNTAX

### ByFactoryName (Default)
```
New-AzureDataFactoryEncryptValue [-DataFactoryName] <String> [[-Value] <SecureString>]
 [[-GatewayName] <String>] [[-Credential] <PSCredential>] [[-Type] <String>] [[-NonCredentialValue] <String>]
 [[-AuthenticationType] <String>] [[-Server] <String>] [[-Database] <String>] [-ResourceGroupName] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByFactoryObject
```
New-AzureDataFactoryEncryptValue [-DataFactory] <PSDataFactory> [[-Value] <SecureString>]
 [[-GatewayName] <String>] [[-Credential] <PSCredential>] [[-Type] <String>] [[-NonCredentialValue] <String>]
 [[-AuthenticationType] <String>] [[-Server] <String>] [[-Database] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The New-AzureDataFactoryEncryptValue cmdlet encrypts sensitive data (e.g.
password, SQL Server connection string) and returns an encrypted value.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> $value = ConvertTo-SecureString "Data Source=servername;Initial Catalog=catelog;user id =user123;password=password123" -AsPlainText -Force PS C:\>New-AzureDataFactoryEncryptValue -GatewayName wikiGateway -DataFactoryName wikiadf -Value $value -ResourceGroupName ADF -Type OnPremisesSqlLinkedService
```

The first command uses the ConvertTo-SecureString cmdlet to convert the specified connection string to a SecureString object, and then stores that object in the $Value variable.
For more information, type Get-Help ConvertTo-SecureString.
Allowed values: SQL or Oracle connection string.

The second command creates an encrypted value for the object stored in $Value for the specified data factory, gateway, resource group, and linked service type."

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> $Value = ConvertTo-SecureString 'Data Source=ContosoServer;Initial Catalog=catalog;Integrated Security=True' -AsPlainText -ForeP5 PS C:\>$Credential = Get-Credential PS C:\>New-AzureDataFactoryEncryptValue -DataFactoryName "WikiADF" -GatewayName "WikiGateway" -ResourceGroupName "ADF" -Value $Value -Credential $Credential -Type OnPremisesSqlLinkedService
```

The first command uses the ConvertTo-SecureString cmdlet to convert the specified connection string to a SecureString object, and then stores that object in the $Value variable.
For more information, type Get-Help ConvertTo-SecureString.
Allowed value: SQL Server connection string. 
The second command uses the Get-Credential cmdlet to collect the windows authentication credential (user name and password), and then stores that PSCredential object in the $Credential variable.
For more information, type Get-Help Get-Credential. 
The third command creates an encrypted value for the object stored in $Value and $Credential for the specified data factory, gateway, resource group, and linked service type.

### -------------------------- EXAMPLE3 --------------------------
```
PS C:\> $Value = ConvertTo-SecureString '\\servername' -AsPlainText -Force PS C:\>$Credential = Get-Credential PS C:\>New-AzureDataFactoryEncryptValue -DataFactoryName "WikiADF" -GatewayName "WikiGateway" -ResourceGroupName "ADF" -Value $Value -Credential $Credential -Type OnPremisesFileSystemLinkedService
```

The first command uses the ConvertTo-SecureString cmdlet to convert the specified string to a SecureString object, and then stores that object in the $Value variable. 
The second command uses the Get-Credential cmdlet to collect the windows authentication credentials (user name and password), and then stores the PSCredential object in the $Credential variable.
For more information about the Get-Credential cmdlet, type Get-HelpGet-Credential. 
The third command creates an encrypted value for the object stored in $Value and $Credential for the specifieddata factory, gateway, resource group, and linked service type.

## PARAMETERS

### -DataFactory
Specifies a  object.
This cmdlet encrypts data for the data factory that this parameter specifies.

```yaml
Type: PSDataFactory
Parameter Sets: ByFactoryObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DataFactoryName
Name of the data factory.

```yaml
Type: String
Parameter Sets: ByFactoryName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GatewayName
Name of the gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the resource group.

```yaml
Type: String
Parameter Sets: ByFactoryName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Value that needs to be encrypted.
For an on-premises SQL Server linked service and an on-premises Oracle linked service, use a connection string.
For an on-premises file system linked service, if the file system is local to the gateway machine, use Local or localhost, and if the file system is on a server different from the gateway machine, use \\\\servername.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the Windows authentication credentials (user name and password) to be used.
This cmdlet encrypts the credential data you specify here.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the linked service type.
This cmdlet encrypts data for the linked service type that this parameter specifies.
Allowed values: OnPremisesSqlLinkedService, OnPremisesOracleLinkedService, and OnPremisesFileSystemLinkedService.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonCredentialValue
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationType
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Database
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
@{Text=}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

