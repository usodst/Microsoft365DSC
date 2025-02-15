# EXOAcceptedDomain

## Description

This resource configures the Accepted Email Domains in Exchange Online.

## Parameters

Ensure

- Required: No (Defaults to 'Present')
- Description: `Present` is the only value accepted.
  Configurations using `Ensure = 'Absent'` will throw an Error!

DomainType

- Required: No (Defaults to 'Authoritative')
- Description: The DomainType parameter specifies the accepted domain type.

Credential

- Required: Yes
- Description: Credentials of a Microsoft 365 Admin

Identity

- Required: Yes
- Description: Domain name of the AcceptedDomain

MatchSubDomains

- Required: No
- Description: MatchSubDomains enables mail to be sent by and received
  from users on any subdomain of this accepted domain.
  MatchSubDomains can only be enabled on an InternalRelay domain.
  The default value is false.

OutboundOnly

- Required: No
- Description: OutboundOnly specifies whether this accepted domain is an
  internal relay domain for the on-premises
  deployment for organizations that have coexistence with a cloud-based organization.
  OutboundOnly can only be enabled if the DomainType parameter is set to Authoritative or InternalRelay.
  The default value is false.

## Example

```PowerShell
EXOAcceptedDomain ExampleEmailDomain {
    Ensure              = 'Present'
    Identity            = 'example.contoso.com'
    MatchSubDomains     = $false
    OutboundOnly        = $false
    Credential          = $Credential
}
```
