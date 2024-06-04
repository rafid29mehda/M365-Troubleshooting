Email forwarding in Microsoft 365 allows you to automatically send incoming emails from one mailbox to another, which can be within the same organization or to an external email address. Here's a brief overview of how it works and the types of email forwarding available:

**How Email Forwarding Works:**
1. **Admin Setup:** As an admin, you can set up email forwarding in the Microsoft 365 admin center. You'll need to access the **Users > Active users** page, select the user, and then manage their email forwarding settings⁴.
2. **User Setup:** Users can set up email forwarding by creating inbox rules in Outlook or through Outlook on the web (OWA), which allows them to forward emails to another address⁵.
3. **License Requirements:** The account from which emails are being forwarded must have a license unless it's a shared mailbox⁴.
4. **Security Controls:** You can use outbound spam filter policies to control automatic forwarding to external recipients to prevent data leakage⁷.

**Types of Email Forwarding:**
1. **Inbox Rules:** Users can create rules in Outlook to automatically forward messages to external senders⁷.
2. **SMTP Forwarding:** Admins can configure SMTP forwarding to automatically send messages to external recipients. They can choose to keep copies of forwarded messages in the mailbox or simply forward them⁷.
3. **Shared Mailbox:** If a user leaves the organization, their mailbox can be converted to a shared mailbox to allow multiple people to access it. However, a shared mailbox cannot exceed 50 GB⁴.

For detailed steps and guidance, you can refer to the Microsoft 365 admin documentation or watch tutorial videos that explain the process in depth¹²³. Remember, it's important to consider the security implications of email forwarding, especially when forwarding to external addresses.

Source: 
(1) [Configure email forwarding - Microsoft 365 admin.](https://learn.microsoft.com/en-us/microsoft-365/admin/email/configure-email-forwarding?view=o365-worldwide.)
(2) [Everything You Need to Know about How to Forward Emails.](https://www.microsoft.com/en-us/microsoft-365-life-hacks/organization/how-to-forward-emails.)
(3) [Control automatic external email forwarding in Microsoft 365.](https://learn.microsoft.com/en-us/defender-office-365/outbound-spam-policies-external-email-forwarding.)
(4) [How Email Forwarding works in Office 365 | Types of email forwarding in Office 365.](https://www.youtube.com/watch?v=fq5LAOlwILU.)
(5) [How to enable email forwarding in Office 365 to multiple internal or external email addresses?.](https://www.youtube.com/watch?v=C45TmddsC4g.)
(6) [How to set up email forwarding in the Exchange admin center: Step-by-step tutorial for Microsoft 365.](https://www.youtube.com/watch?v=GDVsbMBdoMY.)
(7) [Configuring Email Forwarding in Office 365: An Easy Guide.](https://www.sharepointdiary.com/2021/11/configuring-email-forwarding-in-office-365.html.)
(8) [All you need to know about automatic email forwarding in Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/all-you-need-to-know-about-automatic-email-forwarding-in/ba-p/2074888.)
(9) [Automatic email forwarding in Microsoft 365 - CodeTwo.](https://www.codetwo.com/admins-blog/automatic-email-forwarding-microsoft-365/.)




Email forwarding in Microsoft 365 allows users to automatically send incoming emails to another email address. This can be particularly useful for handling emails during absences, redirecting specific types of emails to different departments, or simply consolidating emails into one mailbox. Here's a detailed explanation of how it works and the types of email forwarding available:

## How Email Forwarding Works in Microsoft 365

1. **Automatic Forwarding**: This can be set up by users to automatically forward all emails from their mailbox to another email address. This is typically done through the Outlook settings.
2. **Inbox Rules**: Users can create specific rules in Outlook that forward emails meeting certain criteria (e.g., emails from a specific sender or containing certain keywords) to another email address.
3. **Admin-Configured Forwarding**: Administrators can set up forwarding for any user mailbox in the Exchange admin center, ensuring that all emails sent to a user's mailbox are forwarded to another address.

### Types of Email Forwarding

1. **User-Configured Forwarding**:
   - **Outlook on the Web**: Users can go to Settings > Mail > Forwarding and enter the forwarding email address.
   - **Outlook Desktop**: Users can set up forwarding through the Home tab by managing Rules & Alerts, creating a new rule for forwarding messages【63†source】【64†source】.

2. **Admin-Configured Forwarding**:
   - **Exchange Admin Center (EAC)**:
     1. Go to Recipients > Mailboxes.
     2. Select the mailbox you want to configure.
     3. Under Mailbox > Email forwarding, click Manage email forwarding.
     4. Toggle the setting to ON and enter the forwarding address.
     5. Optionally, select to keep a copy of forwarded messages.
     6. Save your changes【65†source】.

3. **Using CodeTwo Autoresponder for Advanced Forwarding**:
   - For more complex scenarios, such as forwarding emails based on specific conditions or schedules, tools like CodeTwo Autoresponder can be used. This allows for detailed control over forwarding rules, including preventing email loops and setting exceptions【64†source】.

### Example Scenario

**Scenario**: A company wants to ensure that all invoices received by any department are automatically forwarded to the Finance department.

**Solution**:
1. **Using Outlook Inbox Rules**:
   - Users in each department set up a rule in Outlook: Home > Rules > Manage Rules & Alerts > New Rule.
   - Select "Apply rule on messages I receive" and specify conditions like subject contains "invoice".
   - Set the action to "forward it to" the Finance department's email address.
   
2. **Using Admin-Configured Forwarding in EAC**:
   - The admin goes to the EAC, selects each department mailbox, and configures email forwarding to the Finance department's email address.
   - This ensures that all emails, not just those with "invoice" in the subject, are forwarded.

### Monitoring and Control

Admins can monitor and control forwarding to prevent unauthorized data forwarding. This includes setting up outbound spam filter policies and using transport rules to block or allow forwarding based on specific criteria【66†source】.

By understanding these methods, organizations can effectively manage and utilize email forwarding to streamline communication and ensure important emails are directed to the right recipients. For more details, refer to the official Microsoft documentation and support resources.
