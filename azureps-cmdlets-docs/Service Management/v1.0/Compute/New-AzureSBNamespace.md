---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# New-AzureSBNamespace
## SYNOPSIS
Creates a namespace.

## SYNTAX

```
New-AzureSBNamespace [-Name] <String> [[-Location] <String>] [[-CreateACSNamespace] <Boolean>] [-NamespaceType]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The New-AzureSBNamespace cmdlet creates a service namespace for use with Service Bus in Azure.

## EXAMPLES

### 1: Create a service namespace
```
PS C:\> New-AzureSBNamespace -name myNameSpace -Location East US PS C:\> New-AzureSBNamespace myNameSpace 'East US'
```

The following examples create a service namespace for use with Service Bus in Azure.
Both examples include the required parameter values, but only the first includes the parameter names.
The second example can be used because both parameters are positional and their values are given in the required order.

## PARAMETERS

### -CreateACSNamespace
Specifies whether to create an associated ACS namespace in addition to the service namespace.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies a region for the new namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the new namespace.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NamespaceType
Specify a whether to use the namespace for Messaging or Notification Hubs.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Messaging, NotificationHub

Required: True
Position: 4
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AzureSBNamespace](d8478eeb-c378-4806-87e2-ca5732900c4f)

