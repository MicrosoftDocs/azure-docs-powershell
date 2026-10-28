---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Storage.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Storage
ms.date: 10/13/2026
PlatyPS schema version: 2024-05-01
title: New-AzStorageAccount
---

# New-AzStorageAccount

## SYNOPSIS

Create an Azure Storage account.

## SYNTAX

### __AllParameterSets

```
New-AzStorageAccount [-ResourceGroupName] <string> [-Name] <string> [-SkuName] <string>
 [-Location] <string> [-Kind <string>] [-Profile <string>] [-SubscriptionId <string>]
 [-Tag <hashtable>] [-AccessTier <string>] [-MinimumTlsVersion <string>]
 [-PublicNetworkAccess <string>] [-AllowedCopyScope <string>] [-EnableLargeFileShare]
 [-DnsEndpointType <string>] [-EnableHttpsTrafficOnly <bool>] [-AllowBlobPublicAccess <bool>]
 [-AllowSharedKeyAccess <bool>] [-EnableHierarchicalNamespace <bool>] [-EnableSftp <bool>]
 [-EnableLocalUser <bool>] [-EnableExtendedGroups <bool>] [-EnableNfsV3 <bool>]
 [-AllowCrossTenantReplication <bool>] [-DefaultToOAuthAuthentication <bool>] [-EdgeZone <string>]
 [-IdentityType <string>] [-AssignIdentity] [-UserAssignedIdentityId <string>] [-Zone <string[]>]
 [-ZonePlacementPolicy <string>] [-RoutingChoice <string>] [-PublishMicrosoftEndpoint <bool>]
 [-PublishInternetEndpoint <bool>] [-PublishIpv6Endpoint <bool>]
 [-EnableBlobGeoPriorityReplication <bool>] [-KeyExpirationPeriodInDay <int>]
 [-SasExpirationPeriod <timespan>] [-SasExpirationAction <string>] [-EnableAccountLevelImmutability]
 [-ImmutabilityPeriod <int>] [-ImmutabilityPolicyState <string>]
 [-AllowProtectedAppendWrites <bool>] [-Bypass <string[]>] [-DefaultAction <string>]
 [-Subnet <string>] [-VnetName <string>] [-Action <string>] [-IpAddress <string[]>]
 [-Ipv6Address <string[]>] [-EnableAzureActiveDirectoryDomainServicesForFile <bool>]
 [-EnableAzureActiveDirectoryKerberosForFile <bool>]
 [-EnableActiveDirectoryDomainServicesForFile <bool>] [-ActiveDirectoryDomainName <string>]
 [-ActiveDirectoryNetBiosDomainName <string>] [-ActiveDirectoryForestName <string>]
 [-ActiveDirectoryDomainGuid <string>] [-ActiveDirectoryDomainSid <string>]
 [-ActiveDirectoryAzureStorageSid <string>] [-ActiveDirectorySamAccountName <string>]
 [-ActiveDirectoryAccountType <string>] [-DefaultSharePermission <string>] [-EnableSmbOAuth <bool>]
 [-EncryptionKeySource <string>] [-KeyVaultUri <string>] [-KeyName <string>] [-KeyVersion <string>]
 [-RequireInfrastructureEncryption] [-KeyVaultUserAssignedIdentityId <string>]
 [-KeyVaultFederatedClientId <string>] [-EncryptionKeyTypeForTable <string>]
 [-EncryptionKeyTypeForQueue <string>] [-CustomDomainName <string>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Creates an Azure Storage account in the specified resource group.
The account name, location, and SKU are required, and the kind defaults to StorageV2; the account name must be 3-24 characters using lower-case letters and numbers only, and must be globally unique.
Optional parameters cover access tiers, TLS and public access, hierarchical namespace, SFTP and NFS, network rules, customer-managed encryption keys, managed identities, Azure Files identity-based authentication, SAS and key policies, and account-level immutability.
Parameters that are not supplied are omitted from the request so the service default applies.
The cmdlet waits for the long-running create operation to finish and returns the created account.

## EXAMPLES

### Create a general-purpose v2 account

```powershell
New-AzStorageAccount -ResourceGroupName myResourceGroup -Name mystorageaccount -Location eastus -SkuName Standard_LRS -Kind StorageV2
```

### Create a hardened account

Requires TLS 1.2, and disables anonymous blob access and shared key authorization.

```powershell
New-AzStorageAccount -ResourceGroupName myResourceGroup -Name mystorageaccount -Location eastus -SkuName Standard_LRS -Kind StorageV2 -MinimumTlsVersion TLS1_2 -AllowBlobPublicAccess $false -AllowSharedKeyAccess $false -EnableHttpsTrafficOnly $true
```

### Create an account restricted to specific networks

```powershell
New-AzStorageAccount -ResourceGroupName myResourceGroup -Name mystorageaccount -Location eastus -SkuName Standard_LRS -Kind StorageV2 -DefaultAction Deny -Bypass AzureServices -IpAddress 13.64.0.0/16
```

### Create a Data Lake Storage Gen2 account with SFTP

```powershell
New-AzStorageAccount -ResourceGroupName myResourceGroup -Name mystorageaccount -Location eastus -SkuName Standard_LRS -Kind StorageV2 -EnableHierarchicalNamespace $true -EnableSftp $true
```

### Create an account with a customer-managed key

```powershell
New-AzStorageAccount -ResourceGroupName myResourceGroup -Name mystorageaccount -Location eastus -SkuName Standard_LRS -Kind StorageV2 -IdentityType SystemAssigned -KeyVaultUri https://myvault.vault.azure.net/ -KeyName mykey
```

### Create an account with tags

```powershell
New-AzStorageAccount -ResourceGroupName myResourceGroup -Name mystorageaccount -Location eastus -SkuName Standard_LRS -Kind StorageV2 -Tag @{ env = "dev"; owner = "platform" }
```

## PARAMETERS

### -AccessTier

The access tier used for billing. Required when kind is BlobStorage.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Hot
- Cool
- Premium
- Cold
- Smart
HelpMessage: ''
```

### -Action

The action applied to the subnet and IP rules. Defaults to Allow.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Allow
HelpMessage: ''
```

### -ActiveDirectoryAccountType

The Active Directory account type for Azure Storage.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- User
- Computer
HelpMessage: ''
```

### -ActiveDirectoryAzureStorageSid

The security identifier (SID) for Azure Storage.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ActiveDirectoryDomainGuid

The domain GUID.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ActiveDirectoryDomainName

The primary domain the AD DNS server is authoritative for.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ActiveDirectoryDomainSid

The security identifier (SID) of the AD domain.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ActiveDirectoryForestName

The Active Directory forest to get.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ActiveDirectoryNetBiosDomainName

The NetBIOS domain name.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ActiveDirectorySamAccountName

The Active Directory SAMAccountName for Azure Storage.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AllowBlobPublicAccess

Allow or disallow public access to all blobs or containers. The service default is false.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AllowCrossTenantReplication

Allow or disallow cross AAD tenant object replication. The service default is false.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AllowedCopyScope

Restrict copy to and from storage accounts within an AAD tenant or with private links to the same VNet.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- PrivateLink
- AAD
- All
HelpMessage: ''
```

### -AllowProtectedAppendWrites

Allow new blocks to be written to an append blob while maintaining immutability protection. Requires -EnableAccountLevelImmutability.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AllowSharedKeyAccess

Whether the account permits requests authorized with the account access key. The service default is true.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AssignIdentity

Assigns a system-assigned managed identity to the account. -IdentityType takes precedence when both are given.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Bypass

Traffic to bypass the network rules (comma-separated): None, Logging, Metrics, AzureServices. Requires -DefaultAction.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- cf
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -CustomDomainName

The custom domain name assigned to the account. Name is the CNAME source.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -DefaultAction

The action to apply when no network rule matches. Required when any other network rule flag is used.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Allow
- Deny
HelpMessage: ''
```

### -DefaultSharePermission

The default share permission for users using Kerberos authentication when no RBAC role is assigned.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- None
- StorageFileDataSmbShareReader
- StorageFileDataSmbShareContributor
- StorageFileDataSmbShareElevatedContributor
HelpMessage: ''
```

### -DefaultToOAuthAuthentication

Whether the default authentication is OAuth. The service default is false.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -DnsEndpointType

The type of endpoint. AzureDnsZone allows creating a large number of accounts in a single subscription.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Standard
- AzureDnsZone
HelpMessage: ''
```

### -EdgeZone

The name of the edge zone to create the account in.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableAccountLevelImmutability

Enable account-level immutability. Can only be set at creation time.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableActiveDirectoryDomainServicesForFile

Enable Active Directory Domain Services authentication for Azure Files. Requires all Active Directory properties.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableAzureActiveDirectoryDomainServicesForFile

Enable Microsoft Entra Domain Services authentication for Azure Files.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableAzureActiveDirectoryKerberosForFile

Enable Microsoft Entra Kerberos authentication for Azure Files.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableBlobGeoPriorityReplication

Whether Blob Geo Priority Replication is enabled for the account.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableExtendedGroups

Enable extended group support with the local users feature.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableHierarchicalNamespace

Enable a hierarchical namespace (Azure Data Lake Storage Gen2).

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableHttpsTrafficOnly

Allow https traffic only to the storage service. The service default is true.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableLargeFileShare

Allow large file shares. Cannot be disabled once enabled.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableLocalUser

Enable the local users feature.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableNfsV3

Enable NFS 3.0 protocol support.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableSftp

Enable Secure File Transfer Protocol.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableSmbOAuth

Whether managed identities can access SMB shares using OAuth.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EncryptionKeySource

The encryption key source. Inferred as Microsoft.Keyvault when key vault options are supplied.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Microsoft.Storage
- Microsoft.Keyvault
HelpMessage: ''
```

### -EncryptionKeyTypeForQueue

The encryption key type for the Queue service.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Account
- Service
HelpMessage: ''
```

### -EncryptionKeyTypeForTable

The encryption key type for the Table service.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Account
- Service
HelpMessage: ''
```

### -IdentityType

The managed identity type for the account. `SystemAssignedUserAssigned` assigns both a system-assigned and a user-assigned identity.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- SystemAssigned
- UserAssigned
- SystemAssignedUserAssigned
- None
HelpMessage: ''
```

### -ImmutabilityPeriod

The immutability period for blobs since policy creation, in days (1-146000). Requires -EnableAccountLevelImmutability.

```yaml
Type: System.Nullable`1[System.Int32]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ImmutabilityPolicyState

The mode of the account-level immutability policy. Requires -EnableAccountLevelImmutability.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Unlocked
- Locked
- Disabled
HelpMessage: ''
```

### -IpAddress

IPv4 addresses or CIDR ranges to allow (comma-separated). Requires -DefaultAction.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Ipv6Address

IPv6 addresses or CIDR ranges to allow (comma-separated). Requires -DefaultAction.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -KeyExpirationPeriodInDay

Expiration period in days of the key policy assigned to the account.

```yaml
Type: System.Nullable`1[System.Int32]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -KeyName

The name of the key vault key. Must be given together with -KeyVaultUri.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -KeyVaultFederatedClientId

Client id of the multi-tenant application used for cross-tenant customer-managed-key encryption.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -KeyVaultUri

The URI of the key vault. Must be given together with -KeyName.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -KeyVaultUserAssignedIdentityId

Resource id of the user-assigned identity used for server-side encryption.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -KeyVersion

The version of the key vault key. Opts out of implicit key rotation.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Kind

The type of storage account. Defaults to `StorageV2`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Storage
- StorageV2
- BlobStorage
- FileStorage
- BlockBlobStorage
HelpMessage: ''
```

### -Location

The Azure region in which to create the storage account.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 3
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -MinimumTlsVersion

The minimum TLS version permitted on requests to storage. The service default is TLS1_0.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- TLS1_0
- TLS1_1
- TLS1_2
- TLS1_3
HelpMessage: ''
```

### -Name

The name of the storage account. Must be between 3 and 24 characters in length and use numbers and lower-case letters only.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- StorageAccountName
- AccountName
ParameterSets:
- Name: (All)
  Position: 1
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Use the named profile for this command (overrides the active profile).

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -PublicNetworkAccess

Allow, disallow, or let Network Security Perimeter configuration evaluate public network access.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Enabled
- Disabled
- SecuredByPerimeter
HelpMessage: ''
```

### -PublishInternetEndpoint

Whether internet routing storage endpoints are published.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -PublishIpv6Endpoint

Whether IPv6 storage endpoints are published.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -PublishMicrosoftEndpoint

Whether Microsoft routing storage endpoints are published.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -RequireInfrastructureEncryption

Applies a secondary layer of encryption with platform-managed keys.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ResourceGroupName

The resource group name.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -RoutingChoice

The kind of network routing used to deliver user data.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- MicrosoftRouting
- InternetRouting
HelpMessage: ''
```

### -SasExpirationAction

The action performed when the SAS expiration period is violated. Requires -SasExpirationPeriod. Defaults to Log.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Log
- Block
HelpMessage: ''
```

### -SasExpirationPeriod

Expiration period of the SAS policy assigned to the account, as a TimeSpan such as `1.00:00:00` or `(New-TimeSpan -Days 1)`.

```yaml
Type: System.Nullable`1[System.TimeSpan]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SkuName

The SKU name of the storage account.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- StorageAccountType
- AccountType
- Type
ParameterSets:
- Name: (All)
  Position: 2
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Standard_LRS
- Standard_GRS
- Standard_RAGRS
- Standard_ZRS
- Premium_LRS
- Premium_ZRS
- Standard_GZRS
- Standard_RAGZRS
- StandardV2_LRS
- StandardV2_GRS
- StandardV2_ZRS
- StandardV2_GZRS
- PremiumV2_LRS
- PremiumV2_ZRS
HelpMessage: ''
```

### -Subnet

Name or resource id of a subnet. If a name is given, -VnetName is required.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubscriptionId

Azure Subscription Id. Defaults to the subscription of the active profile.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Tag

Resource tags as a hash table of names and values, for example `@{ env = "dev"; owner = "platform" }`.

```yaml
Type: System.Collections.Hashtable
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Tags
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -UserAssignedIdentityId

The ARM resource identifier of the user-assigned identity. Only one is permitted.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -VnetName

Name of the virtual network containing -Subnet.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -WhatIf

Runs the command in a mode that only reports what would happen without performing the actions.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- wi
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Zone

The availability zones to pin the account to (comma-separated).

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ZonePlacementPolicy

The availability zone pinning policy for the account.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Any
- None
HelpMessage: ''
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

You can pipe a resource group name, storage account name, SKU name and location to this cmdlet by property name.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Storage.Models.StorageAccount

The newly-created `StorageAccount` object, including its assigned ARM resource ID, provisioning state, SKU, kind, and service endpoints.

## NOTES

Generated help for storage.

## RELATED LINKS


- [Online Version]()
