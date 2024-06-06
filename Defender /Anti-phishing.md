## Anti-Phishing in Microsoft 365

Anti-phishing policies in Microsoft Defender for Office 365 are essential for protecting users from phishing attempts. These policies can be configured and managed through the Microsoft Defender portal, which offers a variety of options to help ensure that your organization is protected from malicious emails.

#### Configuring Anti-Phishing Policies

1. **Accessing Anti-Phishing Policies**:
   - Go to the Microsoft Defender portal: `Email & Collaboration > Policies & Rules > Threat policies > Anti-phishing`.
   - Select the anti-phishing policy you want to manage from the list.

2. **Policy Settings**:
   - **First Contact Safety Tips**: Enable this feature to inform users when they receive an email from an unfamiliar address, helping them remain vigilant.
   - **Phishing Threshold**: Adjust this setting based on your organization's needs. It determines how aggressively phishing attempts are treated. A lower threshold means more stringent filtering.
   - **Mailbox Intelligence**: Ensures that recipient mailboxes are hosted in Exchange Online to provide better protection.

3. **Modifying Policies**:
   - Edit the settings within each section of the policy to tailor the protection to your needs.
   - Enable or disable policies, change their priority, and delete policies if necessary.

4. **Reporting and Analysis**:
   - Report phishing messages to Microsoft to improve their filtering systems.
   - Inspect message headers to identify why a phishing message might have bypassed filters.

### Scenario-Based Troubleshooting Examples

#### Scenario 1: Phishing Email Bypassed Filtering

**Problem**: A phishing email was delivered to a user’s inbox.

**Steps to Resolve**:
1. **Inspect Message Headers**:
   - Use the Message Header Analyzer to check headers.
   - Look for the `X-Forefront-Antispam-Report` header field for skipped filtering indications (`SCL:-1`).

2. **Adjust Phishing Threshold**:
   - Increase the phishing threshold to a more aggressive level to reduce the likelihood of such emails bypassing filters in the future.

3. **Submit to Microsoft**:
   - Report the phishing email through the Submissions page in the Defender portal to help improve filtering accuracy.

#### Scenario 2: Legitimate Email Quarantined

**Problem**: A legitimate email was quarantined as phishing.

**Steps to Resolve**:
1. **Review Quarantine Details**:
   - Check the quarantine details to understand why the email was flagged.

2. **Whitelist Legitimate Senders**:
   - Use the Tenant Allow/Block List to add legitimate senders to the allow list, ensuring their emails are not quarantined in the future.

3. **Configure SPF, DKIM, and DMARC**:
   - Ensure SPF, DKIM, and DMARC records are properly set up to reduce false positives.

#### Scenario 3: Phishing Email from Spoofed Domain

**Problem**: A phishing email from a spoofed domain was delivered.

**Steps to Resolve**:
1. **Inspect the Spoof Intelligence Insight**:
   - Review the spoof intelligence insight to identify spoofed senders.

2. **Configure Anti-Phishing Policy for Spoofing**:
   - Modify the anti-phishing policy to quarantine suspicious messages from spoofed domains instead of delivering them to junk folders.

3. **Educate Users**:
   - Educate users to use the Report Phishing button in Outlook to report any suspicious emails.

For more detailed information on configuring and managing anti-phishing policies, visit the [Microsoft documentation](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-phishing-policies?view=o365-worldwide)【83†source】【84†source】【85†source】.
