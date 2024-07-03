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














