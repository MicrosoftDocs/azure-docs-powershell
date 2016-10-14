---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
online version: .\Get-AzureRemoteAppCollection.md
schema: 2.0.0
---

# New-AzureRemoteAppCollection

## SYNOPSIS
Creates a RemoteApp collection.

## SYNTAX

### AllParameterSets (Default)
```
New-AzureRemoteAppCollection [-CollectionName] <String> [-ImageName] <String> [-Plan] <String>
 [[-Location] <String>] [-Description <String>] [-CustomRdpProperty <String>] [-ResourceType <CollectionMode>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### AzureVNet
```
New-AzureRemoteAppCollection [-CollectionName] <String> [-ImageName] <String> [-Plan] <String>
 [[-Location] <String>] -VNetName <String> -SubnetName <String> [-DnsServers <String>] [-Domain <String>]
 [-Credential <PSCredential>] [-OrganizationalUnit <String>] [-Description <String>]
 [-CustomRdpProperty <String>] [-ResourceType <CollectionMode>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRemoteAppCollection** cmdlet creates an Azure RemoteApp collection.

## EXAMPLES

### Example 1: Create a RemoteApp collection
```
PS C:\> New-AzureRemoteAppCollection -CollectionName "Contoso" -ImageName "Windows Server 2012 R2" -Plan Standard -Location "West US" -Description CloudOnly
```

This command creates a RemoteApp collection.

### Example 2: Create a RemoteApp collection using credentials
```
PS C:\> $cred = Get-Credential corp.contoso.com\admin
PS C:\> New-AzureRemoteAppCollection -CollectionName "ContosoHybrid" -ImageName "Windows Server 2012 R2" -Plan Standard -VNetName azureVNet -Domain Contoso.com -Credential $cred -Description Hybrid
```

This command creates a RemoteApp collection using a credential from the **Get-Credential** cmdlet.

## PARAMETERS

### -CollectionName
Specifies the name of the RemoteApp collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the credentials of a service account that has permission to join the RemoteApp servers to your domain.

```yaml
Type: PSCredential
Parameter Sets: AzureVNet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomRdpProperty
Specifies custom Remote Desktop Protocal (RDP) properties which can be used to configure drive redirection and other settings.
See RDP Settings for Remote Desktop Services in Windows Serverhttps://technet.microsoft.com/library/ff393699(v=ws.10).aspx (https://technet.microsoft.com/library/ff393699(v=ws.10).aspx) for details.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a short description for the object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DnsServers
Specifies a comma-separated list of IPv4 addresses of the DNS servers.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Domain
Specifies the name of the Active Directory Domain Services domain to which to join the RD Session Host servers.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImageName
Specifies the name of the RemoteApp template image.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the Azure region of the collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OrganizationalUnit
Specifies the name of the organizational unit (OU) to which to join the RD Session Host servers (for example, OU=MyOu,DC=MyDomain,DC=ParentDomain,DC=com).
Attributes such as OU and DC must be in uppercase.
The OU cannot be changed after the collection has been created.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Plan
Specifies the plan for the RemoteApp collection, which may define the usage limits.
Use **Get-AzureRemoteAppPlan** to see the plans available.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### -ResourceType
Specifes the resource type of the collection.
The acceptable values for this parameter are: App or Desktop.

```yaml
Type: CollectionMode
Parameter Sets: (All)
Aliases: 
Accepted values: Unassigned, Apps, Desktop

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubnetName
Specifies the name of the subnet in the virtual network to use to create the RemoteApp collection.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VNetName
Specifies the name of a RemoteApp virtual network.

```yaml
Type: String
Parameter Sets: AzureVNet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppCollection](.\Get-AzureRemoteAppCollection.md)

[Get-AzureRemoteAppPlan](.\Get-AzureRemoteAppPlan.md)

[Remove-AzureRemoteAppCollection](.\Remove-AzureRemoteAppCollection.md)

[Set-AzureRemoteAppCollection](.\Set-AzureRemoteAppCollection.md)

[Update-AzureRemoteAppCollection](.\Update-AzureRemoteAppCollection.md)

