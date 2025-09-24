# AD-Exchange-M365-Localization

Repository for managing localization settings in Active Directory, Exchange, and Microsoft 365.  
Includes reference files for country codes, preferred languages, and time zones.

## Files

- **AD_CountryCode_ISO3166.csv**: ISO 3166 country codes used for the `usageLocation` attribute in Active Directory.
  - When the country is set with MMC tools (ADUC, ADAC), all attributes (_c, co, countryCode_) are updated automatically.
  - If the country is set manually or programmatically (LDAP, PowerShell, C/C++, C#, Java, etc.), these attributes must follow the ISO-3166 standard.
  - This also applies if your Active Directory is synchronized to Azure AD/Office 365.
- **M365_PreferredLanguage.csv**: Supported language codes for Microsoft 365 user attributes such as `preferredLanguage`.
  - Used in Microsoft Entra ID/Office 365 for cloud-only accounts, or in Active Directory if synchronized.
  - Also used with _Set-MailboxRegionalConfiguration Language 'xx-XX'_ to configure mailbox language.
- **Exchange_TimeZones.csv**: Time zone identifiers for Exchange Online mailbox configuration.
  - Used with _Set-MailboxRegionalConfiguration TimeZone 'Time Zone'_ to set mailbox time zones.

## Purpose

These files provide standardized references to configure user attributes such as:

- `c`, `co`, `countryCode` (Active Directory / Azure AD)
- `usageLocation` (Active Directory / Azure AD)
- `preferredLanguage` (Microsoft 365 / Exchange Online)
- `timeZone` (Exchange on-premises / Exchange Online)

## Use cases

- Automating user provisioning in Active Directory and Microsoft 365.
- Bulk updates of mailbox regional settings in Exchange Online.
- Enforcing consistent localization across hybrid or cloud environments.
- Ensuring compliance with ISO standards for country codes.