---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Set-AzureWebsite
## SYNOPSIS
Configures a website running in Azure.

## SYNTAX

```
Set-AzureWebsite [[-Name] <String>] [[-SiteWithConfig] <SiteWithConfig>] [-AppSettings <Hashtable>]
 [-AutoSwapSlotName <String>] [-ConnectionStrings <ConnStringPropertyBag>] [-DefaultDocuments <String[]>]
 [-DetailedErrorLoggingEnabled <Boolean>] [-HandlerMappings <HandlerMapping[]>] [-HostNames <String[]>]
 [-HttpLoggingEnabled <Boolean>] [-ManagedPipelineMode] [-Metadata <List<NameValuePair>>]
 [-NetFrameworkVersion <String>] [-NumberOfWorkers <Int32>] [-PassThru] [-PhpVersion <String>]
 [-RequestTracingEnabled <Boolean>] [-RoutingRules <List<RoutingRule>>] [-Slot <String>]
 [-SlotStickyAppSettingNames <List<String>>] [-SlotStickyConnectionStringNames <List<String>>]
 [-Use32BitWorkerProcess <Boolean>] [-WebSocketsEnabled <Boolean>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Set-AzureWebsite cmdlet configures a website running in Azure.

## EXAMPLES

### 1: Enable HTTP logging for a website
```
PS C:\>Set-AzureWebsite -HttpLoggingEnabled 1
```

This example enables HTTP logging.

### 2: Set storage credentials for a website
```
PS C:\>$settings = New-Object Hashtable$settings[â€œAZURE_STORAGE_ACCOUNTâ€= myaccountname$settings[â€œAZURE_STORAGE_ACCESS_KEYâ€] = myaccesskeySet-AzureWebsite -AppSettings $settings myWebsite
```

This example sets storage credentials in a website named myWebsite with environment variables for AZURE_STORAGE_ACCOUNT and AZURE_STORAGE_ACCESS_KEY.

## PARAMETERS

### -AppSettings
Specifies the environment variables that will be used by the website.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoSwapSlotName
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionStrings
Specifies the connection strings used by the website.

```yaml
Type: ConnStringPropertyBag
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultDocuments
Specifies the documents that are automatically displayed when browsing the website.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DetailedErrorLoggingEnabled
Determines whether detailed IIS errors are logged for the website.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HandlerMappings
Specifies the handler mappings used by the website.

```yaml
Type: HandlerMapping[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostNames
Specifies the fully qualified host names that can be used to access the website.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HttpLoggingEnabled
Determines whether http logging is enabled for the website.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedPipelineMode
Specifies the managed pipeline mode.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Integrated, Classic

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Metadata
Specifies the metadata for the website.

```yaml
Type: List<NameValuePair>
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the website.
\<Whatâ€™s used if this isnâ€™t specified?\>

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetFrameworkVersion
Specifies the version of the .Net Framework required by the website.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberOfWorkers
Specifies the number of worker processes running the website.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns a Boolean value.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhpVersion
Specifies the PHP version required by the website.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequestTracingEnabled
Determines whether request tracing is enabled for the website.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoutingRules
Specifies the routing rules to use for testing in production.

```yaml
Type: List<RoutingRule>
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SiteWithConfig
Specifies the configuration used by the website.

```yaml
Type: SiteWithConfig
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies the slot name of the website.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SlotStickyAppSettingNames
@{Text=}

```yaml
Type: List<String>
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SlotStickyConnectionStringNames
@{Text=}

```yaml
Type: List<String>
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Use32BitWorkerProcess
Specifies whether to enable 32-bit mode.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WebSocketsEnabled
Specifies whether to enable WebSockets.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

