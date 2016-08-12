---
external help file: RMAzure_Storage.xml
online version: 74bc4494-be41-4493-9939-e51e61dd09e6
schema: 2.0.0
---

# New-AzureStorageContext
## SYNOPSIS
Creates an azure_2 Storage context.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureStorageContext [-StorageAccountName] <String> [-Protocol] [-Anonymous] -Environment <String>
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureStorageContext [-StorageAccountName] <String> [-Endpoint <String>] [-Protocol] [-Anonymous]
```

### UNNAMED_PARAMETER_SET_3
```
New-AzureStorageContext -ConnectionString <String>
```

### UNNAMED_PARAMETER_SET_4
```
New-AzureStorageContext [-StorageAccountName] <String> [-StorageAccountKey] <String> [-Endpoint <String>]
 [-Protocol]
```

### UNNAMED_PARAMETER_SET_5
```
New-AzureStorageContext [-StorageAccountName] <String> [-Endpoint <String>] [-Protocol] -SasToken <String>
```

### UNNAMED_PARAMETER_SET_6
```
New-AzureStorageContext [-StorageAccountName] <String> [-StorageAccountKey] <String> [-Protocol]
 -Environment <String>
```

### UNNAMED_PARAMETER_SET_7
```
New-AzureStorageContext [-StorageAccountName] <String> -Environment <String> -SasToken <String>
```

### UNNAMED_PARAMETER_SET_8
```
New-AzureStorageContext [-Local]
```

## DESCRIPTION
The **New-AzureStorageContext** cmdlet creates an azure_2 Storage context.

## EXAMPLES

### Example 1: Create a context by specifying a storage account name and key
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
```

This command creates a context for the account named ContosoGeneral that uses the specified key.

### Example 2: Create a context by specifying a connection string
```
C:\PS>New-AzureStorageContext -ConnectionString "DefaultEndpointsProtocol=https;AccountName=ContosoGeneral;AccountKey=< Storage Key for ContosoGeneral ends with == >;"
```

This command creates a context based on the specified connection string for the account ContosoGeneral.

### Example 3: Create a context for an anonymous storage account
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -Anonymous -Protocol "http"
```

This command creates a context for anonymous use for the account named ContosoGeneral.
The command specifies HTTP as a connection protocol.

### Example 4: Create a context by using the local development storage account
```
C:\PS>New-AzureStorageContext -Local
```

This command creates a context by using the local development storage account.
The command specifies the *Local* parameter.

### Example 5: Get the container for the local developer storage account
```
C:\PS>New-AzureStorageContext -Local | Get-AzureStorageContainer
```

This command creates a context by using the local development storage account, and then passes the new context to the **Get-AzureStorageContainer** cmdlet by using the pipeline operator.
The command gets the azure_2 Storage container for the local developer storage account.

### Example 6: Get multiple containers
```
C:\PS>$Context01 = New-AzureStorageContext -Local 
PS C:\> $Context02 = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
PS C:\> ($Context01, $Context02) | Get-AzureStorageContainer
```

The first command creates a context by using the local development storage account, and then stores that context in the $Context01 variable.

The second command creates a context for the account named ContosoGeneral that uses the specified key, and then stores that context in the $Context02 variable.

The final command gets the containers for the contexts stored in $Context01 and $Context02 by using **Get-AzureStorageContainer**.

### Example 7: Create a context with an endpoint
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >" -Endpoint "contosoaccount.core.windows.net"
```

This command creates an azure_2 Storage context that has the specified storage endpoint.
The command creates the context for the account named ContosoGeneral that uses the specified key.

### Example 8: Create a context with a specified environment
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >" -Environment "AzureChinaCloud"
```

This command creates an azure_2 storage context that has the specified azure_2 environment.
The command creates the context for the account named ContosoGeneral that uses the specified key.

### Example 9: Create a context by using an SAS token
```
C:\PS>$SasToken = New-AzureStorageContainerSASToken -Name "ContosoMain" -Permission "raud"
PS C:\> $Context = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -SasToken $SasToken
PS C:\> $Context | Get-AzureStorageBlob -Container "ContosoMain"
```

The first command generates an SAS token by using the **New-AzureStorageContainerSASToken** cmdlet for the container named ContosoMain, and then stores that token in the $SasToken variable.
That token is for read, add, update, and delete permissions.

The second command creates a context for the account named ContosoGeneral that uses the SAS token stored in $SasToken, and then stores that context in the $Context variable.

The final command lists all the blobs associated with the container named ContosoMain by using the context stored in $Context.

## PARAMETERS

### -Anonymous
Indicates that this cmdlet creates an azure_2 Storage context for anonymous logon.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionString
Specifies a connection string for the azure_2 Storage context.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Endpoint
Specifies the endpoint for the azure_2 Storage context.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Environment
Specifies the azure_2 environment.
psdx_paramvalues AzureCloud and AzureChinaCloud.
For more information, type \[CODE_Snippit\]Get-Help Get-AzureEnvironment\[CODE_Snippit\].

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_6
Aliases: Name,EnvironmentName

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: Name,EnvironmentName

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Local
Indicates that this cmdlet creates a context by using the local development storage account.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_8
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies the protocol permitted for a request made with the account SAS.
psdx_paramvalues

-- HttpsOnly
-- HttpsOrHttp

The default value is HttpsOrHttp.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6
Aliases: 
Accepted values: Http, Https

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SasToken
Specifies a Shared Access Signature (SAS) token for the context.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_7
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountKey
Specifies an azure_2 Storage account key.
This cmdlet creates a context for the key that this parameter specifies.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
Specifies an azure_2 Storage account name.
This cmdlet creates a context for the account that this parameter specifies.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### AzureStorageContext

## NOTES

## RELATED LINKS

[Get-AzureStorageBlob](74bc4494-be41-4493-9939-e51e61dd09e6)

[New-AzureStorageContainerSASToken](dc3564e2-9ede-4901-8d62-f49017a03281)

