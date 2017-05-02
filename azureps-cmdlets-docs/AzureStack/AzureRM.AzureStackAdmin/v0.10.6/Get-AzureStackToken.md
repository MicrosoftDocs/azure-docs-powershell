---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureStackToken

## SYNOPSIS
Gets a token that is used to make calls to the Azure stack resource manager.

## SYNTAX

### ADFS (Default)
```
Get-AzureStackToken [-Authority] <String> [-Resource <String>] [-ClientId <String>]
 [-Credential <PSCredential>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

### AAD
```
Get-AzureStackToken [-Authority] <String> -Resource <String> -AadTenantId <String> [-ClientId <String>]
 [-Credential <PSCredential>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStackToken** cmdlet gets a token that is used to make calls to the Azure stack resource manager.

## EXAMPLES

### Example 1: Get an access token for a specified user
```
$Endpoints = Invoke-RestMethod -Method Get -Uri "$($ArmEndpoint.TrimEnd('/'))/metadata/endpoints?api-version=2015-01-01" -Verbose
$AAdAuthorityEndpoint = $Endpoints.authentication.loginEndpoint
$AAdResource = $Endpoints.authentication.audiences\[0\]

Get-AzureStackToken -Authority $AAdAuthorityEndpoint -AadTenantId $AadTenantId -Resource $AAdResource -Credential (Get-Credential) -Verbose
```

The first command gets the login endpoints and stores the result in the variable named $Endpoints.
The second command gets the authentication information and stores the result in the variable named $AAdAuthorityEndpoint.
The third command gets the users from the $Endpoints variable and stores the result in the variable named $AAdResource.
The forth command gets the access token for the specified user.

## PARAMETERS

### -AadTenantId
Specifies the Azure active directory (AAD) tenant ID of the user belonging to the AAD tenant group.

```yaml
Type: String
Parameter Sets: AAD
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authority
Specifies the endpoint for authentication, typically of the form "https://login.windows.net". To obtain this value, access the Azure resource manager (ARM) metadata endpoint https://\<ArmUri\>/metadata/endpoints?api-version=2015-01-01 and read the value of **loginEndpoint**.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientId
Specifies the client ID for the Azure Stack token.

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

### -Credential
Specifies the credential for the user for whom we need the access token.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa
Accepted values: SilentlyContinue, Stop, Continue, Inquire

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies a variable that is used for storing an informational message.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Specifies a variable that stores the value of the current pipeline element.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resource
Specifies the resource for authentication.
To obtain this value, access the Azure resource manager (ARM) metadata endpoint `https://<ArmUri>/metadata/endpoints?api-version=2015-01-01` and read the value of **audiences**.

```yaml
Type: String
Parameter Sets: ADFS
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: AAD
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
