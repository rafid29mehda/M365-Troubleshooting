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
