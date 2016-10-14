---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureWebsiteDeployment

## SYNOPSIS
Gets the deployments for a website.

## SYNTAX

```
Get-AzureWebsiteDeployment [[-CommitId] <String>] [[-MaxResults] <Int32>] [-Details] [[-Name] <String>]
 [-Slot <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

Gets the deployments for a website in Azure.

## EXAMPLES

### 1: Get all deployments for a website
```
PS C:\>Get-AzureWebsiteDeployment -Name mySite
```

This example gets all deployments for an Azure website named 'mySite'.

### 2: Get information about a specific deployment
```
PS C:\>Get-AzureWebsiteDeployment -Name mySite -CommitId f87654321 -Details
```

This example gets detailed information about deployment 'f87654321' for an Azure website named 'mySite'.

## PARAMETERS

### -CommitId
Specifies the unique ID for the deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxResults
Specifies the largest number of results that you want the command to return.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Details
Shows detailed information about the deployments.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the website for which you want to get deployment information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Specifies the slot name.

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

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Restore-AzureWebsiteDeployment](.\Restore-AzureWebsiteDeployment.md)

[Save-AzureWebsiteLog](.\Save-AzureWebsiteLog.md)

