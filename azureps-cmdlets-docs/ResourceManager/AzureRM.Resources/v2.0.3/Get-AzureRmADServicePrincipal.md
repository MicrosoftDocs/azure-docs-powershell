---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmADServicePrincipal

## SYNOPSIS
Filters active directory service principals.

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzureRmADServicePrincipal [-ServicePrincipalName <String>]
```

### SearchStringParameterSet
```
Get-AzureRmADServicePrincipal -SearchString <String>
```

### ObjectIdParameterSet
```
Get-AzureRmADServicePrincipal -ObjectId <Guid>
```

### SPNParameterSet
```
Get-AzureRmADServicePrincipal -ServicePrincipalName <String>
```

## DESCRIPTION
Filters active directory service principals.

## EXAMPLES

### --------------------------  Filters service principals using SPN  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Get-AzureRmADServicePrincipal -SPN 36f81fc3-b00f-48cd-8218-3879f51ff39f
```

Gets service principals with 36f81fc3-b00f-48cd-8218-3879f51ff39f SPN

### --------------------------  Filters service principals using Search String  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Get-AzureRmADServicePrincipal -SearchString Web
```

Filters all ad service principals that has Web in the display name.

### --------------------------  List AD service principals  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Get-AzureRmADServicePrincipal
```

Gets all AD service principals

## PARAMETERS

### -ServicePrincipalName
SPN of the service.

```yaml
Type: String
Parameter Sets: EmptyParameterSet
Aliases: SPN

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: SPNParameterSet
Aliases: SPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SearchString
The service principal display name

```yaml
Type: String
Parameter Sets: SearchStringParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
Object id of the service principal.

```yaml
Type: Guid
Parameter Sets: ObjectIdParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmADGroup]()

[Get-AzureRmADUser]()

[Get-AzureRmADGroupMember]()

