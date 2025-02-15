﻿# EXOHostedContentFilterRule

## Parameters

| Parameter | Attribute | DataType | Description | Allowed Values |
| --- | --- | --- | --- | --- |
| **Identity** | Key | String | The Identity parameter specifies the name of the HostedContentFilter rule that you want to modify. ||
| **HostedContentFilterPolicy** | Required | String | The HostedContentFilterPolicy parameter specifies the name of the HostedContentFilter policy that's associated with the HostedContentFilter rule. ||
| **Enabled** | Write | Boolean | Specify if this rule should be enabled. Default is $true. ||
| **Priority** | Write | UInt32 | The Priority parameter specifies a priority value for the rule that determines the order of rule processing. A lower integer value indicates a higher priority, the value 0 is the highest priority, and rules can't have the same priority value. ||
| **Comments** | Write | String | The Comments parameter specifies informative comments for the rule, such as what the rule is used for or how it has changed over time. The length of the comment can't exceed 1024 characters. ||
| **ExceptIfRecipientDomainIs** | Write | StringArray[] | The ExceptIfRecipientDomainIs parameter specifies an exception that looks for recipients with email address in the specified domains. You can specify multiple domains separated by commas. ||
| **ExceptIfSentTo** | Write | StringArray[] | The ExceptIfSentTo parameter specifies an exception that looks for recipients in messages. You can use any value that uniquely identifies the recipient. ||
| **ExceptIfSentToMemberOf** | Write | StringArray[] | The ExceptIfSentToMemberOf parameter specifies an exception that looks for messages sent to members of groups. You can use any value that uniquely identifies the group. ||
| **RecipientDomainIs** | Write | StringArray[] | The RecipientDomainIs parameter specifies a condition that looks for recipients with email address in the specified domains. You can specify multiple domains separated by commas. ||
| **SentTo** | Write | StringArray[] | The SentTo parameter specifies a condition that looks for recipients in messages. You can use any value that uniquely identifies the recipient. ||
| **SentToMemberOf** | Write | StringArray[] | The SentToMemberOf parameter looks for messages sent to members of groups. You can use any value that uniquely identifies the group. ||
| **Ensure** | Write | String | Specify if this rule should exist or not. |Present, Absent|
| **Credential** | Write | PSCredential | Credentials of the Exchange Global Admin ||
| **ApplicationId** | Write | String | Id of the Azure Active Directory application to authenticate with. ||
| **TenantId** | Write | String | Id of the Azure Active Directory tenant used for authentication. ||
| **CertificateThumbprint** | Write | String | Thumbprint of the Azure Active Directory application's authentication certificate to use for authentication. ||
| **CertificatePassword** | Write | PSCredential | Username can be made up to anything but password will be used for CertificatePassword ||
| **CertificatePath** | Write | String | Path to certificate used in service principal usually a PFX file. ||

# EXOHostedContentFilterRule

### Description

This resource configures an Hosted Content Filter Rule in Exchange Online.
Reference: https://docs.microsoft.com/en-us/powershell/module/exchange/advanced-threat-protection/new-HostedContentFilterRule?view=exchange-ps

## Parameters

HostedContentFilterPolicy

- Required: Yes
- Description: The Identity of the HostedContentFilter Policy to
  associate with this HostedContentFilter Rule.

Ensure

- Required: No (Defaults to 'Present')
- Description: `Present` is the only value accepted.
    Configurations using `Ensure = 'Absent'` will throw an Error!

Credential

- Required: Yes
- Description: Credentials of the account to authenticate with

Identity

- Required: Yes
- Description: Domain name of the AcceptedDomain

## Example

```PowerShell
        EXOHostedContentFilterRule TestHostedContentFilterRule {
            Ensure = 'Present'
            Identity = 'TestRule'
            Credential = $Credential
            HostedContentFilterPolicy = 'TestPolicy'
            Enabled = $true
            Priority = 0
            RecipientDomainIs = @('contoso.com')
        }
```


