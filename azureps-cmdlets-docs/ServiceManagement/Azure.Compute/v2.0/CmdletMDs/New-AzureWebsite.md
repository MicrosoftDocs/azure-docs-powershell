---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureWebsite

## SYNOPSIS
Create a new website to run in Azure.

## SYNTAX

```
New-AzureWebsite [[-Location] <String>] [[-Hostname] <String>] [[-PublishingUsername] <String>] [-Git]
 [-GitHub] [-GithubCredentials <PSCredential>] [-GithubRepository <String>] [[-Name] <String>]
 [[-Slot] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The cmdlet creates a new website to run in Azure and prepares for deployment through Github.

## EXAMPLES

### 1: Create a new website with Git
```
PS C:\>New-AzureWebsite mySite -Git
```

This example creates a new website in Azure and a local Git repository to use for deploying files to the new website.

### 2: Create website integrated with Github
```
PS C:\>New-AzureWebsite mysite -Github -GithubRepository myaccount/myrepo
```

This example creates a new website linked to a Github repository named myaccount/myrepo.
Commits to the Github repository are pushed to the website in Azure.

## PARAMETERS

### -Location
Specifies the location of the data center where you want to deploy the website.

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

### -Hostname
Specifies an alternative host name for the new website.

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

### -PublishingUsername
The user name you have specified in the Azure Portal for Git deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Git
Sets up a local Git repository and links it to the website.
If specified, this parameter sets up a Git repository in the local directory and add a remote repository named 'azure' that links to the website in Azure.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GitHub
If enabled, this parameter links the new website to an existing Github repository.
Commits to the Giuthub repository are pushed to the website in Azure.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GithubCredentials
Specifies the user name and password credentials to connect to Github.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GithubRepository
Specifies the full name of the Github repository to link to this website.
For example, myaccount/myrepo.

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

### -Name
Specifies a name for the website.

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
Specifies a slot name for the website.

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

[Set-AzureWebsite](.\Set-AzureWebsite.md)

