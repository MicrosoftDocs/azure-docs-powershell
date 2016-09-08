---
external help file: RMAzure_Storage.xml
online version: f08d2de2-a276-439c-b9a8-ee187a8c334e
schema: 2.0.0
---

# New-AzureStorageAccountSASToken
## SYNOPSIS
Creates an SAS token.

## SYNTAX

```
New-AzureStorageAccountSASToken [-Context <AzureStorageContext>] [-ExpiryTime <DateTime>]
 [-IPAddressOrRange <String>] [-Permission <String>] [-Protocol <SharedAccessProtocol>] [-StartTime <DateTime>]
 [-ResourceType] [-Service]
```

## DESCRIPTION
The **New-AzureStorageSASToken** cmdlet creates an account-level shared access signature (SAS) token for an azure_2 Storage account.

You can use the SAS token to delegate permissions for multiple services, or to delegate permissions for services not available with an object-level SAS token.

## EXAMPLES

### Example 1: Create an SAS token
```
PS C:\> New-AzureStorageAccountSASToken -Service Blob,File,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup"
```

This command creates an account-level SAS token with full permission.

### Example 2: Create an SAS token for a range of IP addresses
```
PS C:\> New-AzureStorageAccountSASToken -Service Blob,File,Table,Queue -ResourceType Service,Container,Object -Permission "racwdlup" -Protocol HttpsOnly -IPAddressOrRange 168.1.5.60-168.1.5.70
```

This command creates an SAS token for HTTPS-only requests from the specified range of IP addresses.

## PARAMETERS

### -Context
Specifies the azure_2 storage context.
You can use the New-AzureStorageContext cmdlet to get an **AzureStorageContext** object.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -ExpiryTime
Specifies the time at which the shared access signature becomes invalid.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddressOrRange
Specifies the IP address or range of IP addresses from which to accept requests, such as 168.1.5.65 or 168.1.5.60-168.1.5.70.
The range is inclusive.

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

### -Permission
Specifies the permissions for Storage account.
Permissions are valid only if they match the specified resource type.
For more information about acceptable permission values, see Constructing an Account SAShttp://go.microsoft.com/fwlink/?LinkId=799514

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

### -Protocol
Specifies the protocol permitted for a request made with the account SAS.
psdx_paramvalues

-- HttpsOnly
-- HttpsOrHttp

The default value is HttpsOrHttp.

```yaml
Type: SharedAccessProtocol
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceType
Specifies the resource types that are available with the SAS token.
psdx_paramvalues

-- None
-- Service
-- Container
-- Object

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: None, Service, Container, Object

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service
Specifies the service.
psdx_paramvalues

-- None
-- Blob
-- File
-- Queue
-- Table

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: None, Blob, File, Queue, Table

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies the time, as a **DateTime** object, at which the SAS becomes valid.
To get a **DateTime** object, use the Get-Date cmdlet.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageBlobSASToken](f08d2de2-a276-439c-b9a8-ee187a8c334e)

[New-AzureStorageContainerSASToken](dc3564e2-9ede-4901-8d62-f49017a03281)

[New-AzureStorageFileSASToken](4fb064f5-94bc-4d8f-9ef6-2611f8aab99c)

[New-AzureStorageQueueSASToken](6cae6e32-2800-4c20-88ae-d40271476628)

[New-AzureStorageShareSASToken](07c8ad4e-7a32-4407-9120-1432126b7376)

[New-AzureStorageTableSASToken](abee1cab-f04a-400e-8fb1-caed1ee02ee7)

