---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: FDBADDCD-A474-42F9-89BA-0BEC56D51A05
---

# Get-AzureStackToken

## SYNOPSIS
Gets a token to be used to make calls to Azure Stack Resource Manager.

## SYNTAX

### ADFS (Default)
```
Get-AzureStackToken [-Authority] <String> [-Resource <String>] [-ClientId <String>]
 [-Credential <PSCredential>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

### AAD
```
Get-AzureStackToken [-Authority] <String> -Resource <String> -AadTenantId <String> [-ClientId <String>]
 [-Credential <PSCredential>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

## DESCRIPTION
The **Get-AzureStackToken** cmdlet gets a token to be used to make calls to Azure Stack Resource Manager.
The cmdlet will be deprecated in a future release.

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
Specifies the Azure Active Directory (AAD) tenant ID of the user belonging to the AAD tenant group.

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
Specifies the authority endpoint for authentication, typically of the form https://login.contoso.net.
The value can be obtained by access the ARM metadata endpoint https://\<ArmUri\>/metadata/endpoints?api-version=2015-01-01 and reading the value of loginEndpoint.

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
The *ClientId* parameter is optional.
This parameter will be removed in a future release.

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
The acceptable values for this parameter are:
* Continue
* Ignore
* Inquire
* SilentlyContinue
* Stop
* Suspend

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
Specifies an information variable.

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
Stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.

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
Specifies the resource value for authentication. The value can be obtained by access the ARM metadata endpoint https://\<ArmUri\>/metadata/endpoints?api-version=2015-01-01 and getting the value of audiences.

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

## INPUTS

## OUTPUTS

### System.Object

## NOTES
## RELATED LINKS
