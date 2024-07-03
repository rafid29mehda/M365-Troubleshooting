Customers often list the wrong values in their SPF record, which can cause mail flow problems.

**MX (mail exchanger) records** provide an easy way for mail servers to know where to send email.

**SPF (sender policy framework)** is a specially formatted TXT record in DNS. SPF validates that only the organization that owns a domain is actually sending email from that domain. SPF is a security measure that helps makes sure someone doesn't impersonate another organization. This impersonation is often called spoofing. As a domain owner, you can use SPF to publish a list of IP addresses or subnets that are authorized to send email on your organization's behalf. This can be helpful if you want to send email from multiple servers or services with different IP addresses. You can only have one SPF record per domain. Having multiple SPF records will invalidate all SPF records and cause mail flow problems.

