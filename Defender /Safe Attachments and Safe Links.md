## Safe Attachments and Safe Links Policies in Microsoft Defender for Office 365

**Safe Attachments Policies:**

Safe Attachments in Microsoft Defender for Office 365 is designed to protect your email system from malicious attachments. Here’s how it works and how you can configure it:

1. **Actions and Notifications:**
   - **Monitor**: This action tracks the scanning results without blocking the message. It's useful for testing new policies.
   - **Block**: Blocks the delivery of emails with malicious attachments by quarantining them.
   - **Dynamic Delivery**: Delivers the email body immediately but holds the attachment until scanning is complete. If no threats are found, the attachment is then delivered. This helps maintain email flow while ensuring attachments are safe.

2. **Configuration Steps:**
   - Go to the Microsoft 365 Defender portal.
   - Navigate to Email & collaboration > Policies & rules > Threat policies.
   - Select Safe Attachments and create a new policy or modify an existing one.
   - Set the actions (Monitor, Block, or Dynamic Delivery) based on your organizational needs.
   - Apply the policy to the appropriate users or groups.

3. **False Positives Handling:**
   - If legitimate attachments are blocked, report false positives through the Microsoft 365 Defender portal. Adjust the policies accordingly based on the feedback from these reports.

**Safe Links Policies:**

Safe Links in Microsoft Defender for Office 365 protects users from malicious URLs in emails and Office documents by scanning and rewriting URLs to check for potential threats. Here’s a breakdown of how Safe Links operates and how to set it up:

1. **How Safe Links Works:**
   - When a user clicks on a URL in an email or document, Safe Links checks the URL against a list of known malicious sites.
   - If the URL is deemed safe, the user is redirected to the intended site.
   - If the URL is malicious, the user is presented with a warning page.

2. **Configuration Steps:**
   - Access the Microsoft 365 Defender portal.
   - Go to Email & collaboration > Policies & rules > Threat policies.
   - Select Safe Links and create a new policy or edit an existing one.
   - Configure the settings, such as turning on real-time URL scanning and enabling protection for Microsoft Teams, Office applications, and email.
   - Apply the policy to the desired users or groups.

3. **Scenarios and Priority:**
   - You can set priorities for Safe Links policies to ensure the most critical policies take precedence.
   - For example, a custom policy with a priority of 0 will take the highest precedence over other policies.

4. **Safe Links for Microsoft Teams and Office Apps:**
   - Safe Links protection extends to Microsoft Teams, checking URLs in chats, channels, and tabs.
   - In Office apps, Safe Links checks URLs in Word, Excel, PowerPoint, and other supported Office applications when documents are opened.

By configuring Safe Attachments and Safe Links policies, you can significantly enhance the security of your organization's email and collaboration tools, protecting against a wide range of threats.

For more detailed information, you can visit:
- [Microsoft Learn: Safe Attachments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/keeping-your-email-safe-with-microsoft-defender-for-office-365/ba-p/2270377)【73†source】
- [Microsoft Learn: Safe Links](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-links)【75†source】
