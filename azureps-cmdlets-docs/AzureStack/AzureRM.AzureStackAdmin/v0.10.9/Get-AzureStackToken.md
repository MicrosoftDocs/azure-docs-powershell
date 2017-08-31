---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml

online version: 
schema: 2.0.0
---

# Get-AzureStackToken

## SYNOPSIS
Gets a token that is used to make calls to the Resource Manager.

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
The Get-AzureStackToken cmdlet gets a token to be used to make calls to Azurestack Resource Manager.
The cmdlet will be deprecated in a future release.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$ArmEndpoint = "https://adminmanagement.local.azurestack.external"
$endpoints = Invoke-RestMethod -Method Get -Uri "$($ArmEndpoint.TrimEnd('/'))/metadata/endpoints?api-version=2015-01-01" -Verbose
$aadAuthorityEndpoint = $endpoints.authentication.loginEndpoint
$aadResource = $endpoints.authentication.audiences[0]
$AadTenantId = "<AAD tenant that you used to deploy Azure Stack>"

Get-AzureStackToken -Authority $aadAuthorityEndpoint -AadTenantId $AadTenantId -Resource $aadResource 

```

Description

-----------

The following example gets the access token for the specified user

## PARAMETERS

### -AadTenantId
Azure active directory(AAD) tenant Id of the user belonging to the  AAD tenant group.

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
Authority endpoint for authentication, typically of the form https://login.windows.net.
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
The ClientId parameter is optional. This parameter will be removed in a future release.

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
Specifies how this cmdlet responds to an information event. The following values are permitted for this object type.

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
Resource value for authentication, The value can be obtained by access the ARM metadata endpoint https://\<ArmUri\>/metadata/endpoints?api-version=2015-01-01 and reading the value of audiences.

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


