## Troubleshoot SMTP mail flow

### - Mail Trace

### - Microsoft Remote Connectivity Analyzer
To test SMTP, you can use the Microsoft Remote Connectivity Analyzer to perform SMTP inbound and outbound tests:

In Microsoft Edge, navigate to the Microsoft Remote Connectivity Analyzer website: Microsoft Remote Connectivity Analyzer.

If necessary, select Office 365 in the navigation pane and then select the test you want to perform:

Inbound SMTP Email. Steps through the process used by an email server to send email to your organization using SMTP. Identifies potential problems with your configuration.
Outbound SMTP Email. Checks your outbound configuration, including reverse DNS, Sender ID, and remote blocklist (RBL) checks. Identifies potential problems with your configuration. 

### - Review your configuration
Having run these SMTP tests, and determined where the problem lies, you can investigate your configuration more closely. Things to check in the Exchange admin center include:

Accepted domains. Your default domain and any custom domains should be displayed.
Remote domains. A single domain called Default displays. If you add more, you can control the type of messages that can be routed to the domain. For example: out-of-office replies, automatic forwarding, and delivery reports.
Connectors. You use connectors to control message flow to specific domains, and any configuration issues can prevent routing.
Mail flow rules. You can configure mail flow rules to route messages to use a specific connector.
Users' email addresses. Your users require an email address for any custom domain you add.

### - Analyze DSN/NDR messages
A DSN/NDR notification message displays a status code and possible cause for nondelivery, along with the internal or external host that generated the notification. If an external host is generating notifications, you may have to work with the receiving organization’s messaging administrator to resolve the issue or clarify the reason the email isn't being delivered. If a server in your Exchange organization is generating the notifications, you may have to reconfigure a transport component or troubleshoot to isolate the issue.

Common NDR codes:

#### NDR code	Description

**5.1.1	Recipients email address does not exist**

**5.2.x	Number of messages permitted to be sent or received per hour exceeded**

**5.7.x	Sender denied by sending or receiving system**


### - Analyze message headers
When email messages reach their destination but were noticeably delayed, you can analyze the original message headers to determine the amount of time that elapsed during each hop of the email routing process. Analyzing message headers is a quick and effective troubleshooting technique that helps you isolate the source of the delay and enables you to determine whether the source is internal or external to your Exchange organization. By default, the original message headers aren't displayed in most mail clients, but you usually can retrieve them.

If you want to retrieve them in Outlook, open the affected message, select File, and then select Properties. In the Properties dialog box, you'll see the message headers in the Internet headers field. However, this information may be difficult to decipher. As such, you can copy the message header text and use the Message Analyzer function of the Microsoft Remote Connectivity Analyzer tool to display the information in an easy-to-read format.

#
#
#

Customers often list the wrong values in their SPF record, which can cause mail flow problems.

**MX (mail exchanger) records**

provide an easy way for mail servers to know where to send email. For the best mail flow experience (especially for spam filtering) we recommend pointing the MX record for your organization's domain to Microsoft 365 or Office 365. If your MX record doesn't point to Microsoft 365 or Office 365, there will be some valid messages that the service misclassifies as spam and some spam messages that the service misclassifies as legitimate email.

**SPF (sender policy framework)**

is a specially formatted TXT record in DNS. SPF validates that only the organization that owns a domain is actually sending email from that domain. SPF is a security measure that helps makes sure someone doesn't impersonate another organization. This impersonation is often called spoofing. As a domain owner, you can use SPF to publish a list of IP addresses or subnets that are authorized to send email on your organization's behalf. This can be helpful if you want to send email from multiple servers or services with different IP addresses. You can only have one SPF record per domain. Having multiple SPF records will invalidate all SPF records and cause mail flow problems.

**DomainKeys Identified Mail (DKIM)**

lets you attach a digital signature to email messages in the message header of emails you send. Email systems that receive email from your domain use this digital signature to determine if incoming email that they receive is legitimate. 

**Domain-based Message Authentication, Reporting, and Conformance (DMARC)**

helps receiving mail systems determine what to do with messages that fail SPF or DKIM checks and provides another level of trust for your email partners. 

There are no admin portals or PowerShell cmdlets in Microsoft 365 for you to manage DMARC TXT records in your custom domains. Instead, you create the DMARC TXT record at your domain registrar or DNS hosting service (often the same company).


The **Autodiscover record**

allows client computers to automatically find Exchange and configure the client properly.














