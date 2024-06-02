Setting up a DNS server for Microsoft 365 from scratch involves configuring your DNS settings to integrate your domain with Microsoft 365 services. This does not involve creating a DNS server from scratch, but rather configuring an existing DNS service for Microsoft 365 use. Below is a comprehensive step-by-step guide with a detailed example scenario.

## Step-by-Step Guide to Setting Up DNS for Microsoft 365

### Scenario: Acme Corporation Setting Up DNS for Microsoft 365

**Objective**: Configure the DNS settings for the domain `acmecorp.com` to work with Microsoft 365 services.

#### Step 1: Sign in to Microsoft 365 Admin Center

1. **Open Your Web Browser**:
   - Navigate to [admin.microsoft.com](https://admin.microsoft.com).

2. **Sign In**:
   - Enter your Microsoft 365 admin account credentials to sign in.

#### Step 2: Add Your Domain to Microsoft 365

1. **Navigate to Settings**:
   - In the left-hand navigation pane, click on `Settings` > `Domains`.

2. **Add a Domain**:
   - Click on `Add domain`.

3. **Enter Your Domain Name**:
   - Type in your custom domain name (e.g., `acmecorp.com`), then click `Use this domain`.

4. **Verify Domain Ownership**:
   - Microsoft 365 will provide a TXT record that you need to add to your DNS host to verify domain ownership.

**Example Steps**:
```plaintext
Admin Portal -> Settings -> Domains -> Add domain -> Enter acmecorp.com -> Use this domain.
```

#### Step 3: Verify Domain Ownership with Your DNS Host

**Example DNS Host: GoDaddy**

1. **Log in to GoDaddy**:
   - Access your GoDaddy account at [GoDaddy Login](https://www.godaddy.com).

2. **Navigate to DNS Management**:
   - Go to `My Products`.
   - Find your domain (e.g., `acmecorp.com`) and click `DNS` to manage settings.

3. **Add a TXT Record**:
   - Under `Records`, click `Add`.
   - Select `TXT` as the record type.
   - Enter the details provided by Microsoft 365:
     - **Host**: @
     - **TXT Value**: The value provided by Microsoft 365 (e.g., `MS=ms12345678`).
     - **TTL**: 1 hour (3600 seconds).
   - Save the record.

**Example Steps**:
```plaintext
GoDaddy -> My Products -> Select Domain -> DNS -> Add -> Select TXT -> Enter provided TXT record -> Save.
```

4. **Verify the Domain in Microsoft 365**:
   - Return to the Microsoft 365 Admin Center.
   - Click `Verify` to confirm the TXT record has been added correctly.

#### Step 4: Configure DNS Records for Microsoft 365 Services

After verifying your domain, you need to configure the required DNS records for Microsoft 365 services.

1. **Navigate to DNS Settings**:
   - Go to `Settings` > `Domains` in the Microsoft 365 Admin Center.
   - Click on your domain name.
   - Click on `DNS settings`.

2. **Add DNS Records**:
   - Microsoft 365 will provide a list of DNS records you need to configure, including:
     - **MX Record** (for mail flow): Directs email to your Microsoft 365 mailboxes.
     - **CNAME Records** (for Autodiscover and other services): Helps configure email clients automatically.
     - **TXT Records** (for SPF): Helps prevent email spoofing.
     - **SRV Records** (for Skype for Business and Teams): Enables these services.

**Example DNS Record Configurations**:

**MX Record**:
```plaintext
Type: MX
Host: @
Points to: <MX endpoint provided by Microsoft 365>
Priority: 0
TTL: 1 hour (3600 seconds)
```

**CNAME Record (Autodiscover)**:
```plaintext
Type: CNAME
Host: autodiscover
Points to: autodiscover.outlook.com
TTL: 1 hour (3600 seconds)
```

**TXT Record (SPF)**:
```plaintext
Type: TXT
Host: @
TXT Value: v=spf1 include:spf.protection.outlook.com -all
TTL: 1 hour (3600 seconds)
```

**SRV Record (Skype for Business / Teams)**:
```plaintext
Type: SRV
Service: _sip
Protocol: _tls
Name: @
Priority: 100
Weight: 1
Port: 443
Target: sipdir.online.lync.com
TTL: 1 hour (3600 seconds)
```

3. **Log in to Your DNS Host (GoDaddy Example)**:
   - Access your DNS hosting provider’s management console (e.g., GoDaddy).
   - Add each of the DNS records provided by Microsoft 365.

**Example Steps for GoDaddy**:
```plaintext
GoDaddy -> My Products -> Select Domain -> DNS -> Add Record.
Add MX, CNAME, TXT, and SRV records as specified by Microsoft 365.
```

#### Step 5: Validate DNS Configuration

1. **Check DNS Records in Microsoft 365**:
   - Return to the Microsoft 365 Admin Center.
   - Microsoft 365 will automatically check if the DNS records are configured correctly.
   - You will see a status indicator confirming the setup.

2. **Verify Email Flow and Service Availability**:
   - Send test emails to ensure the MX record is working.
   - Check Autodiscover for email clients.
   - Verify that Skype for Business and Teams are functioning.

**Example Steps**:
```plaintext
Admin Portal -> Settings -> Domains -> Check DNS settings.
Send test emails, verify Autodiscover, and ensure Teams is working.
```

### Conclusion

By following these detailed steps, Acme Corporation can successfully set up DNS for their domain `acmecorp.com` in Microsoft 365, ensuring that all services, such as email and collaboration tools, work seamlessly.

### Example Summary for Acme Corporation

1. **Add and Verify Domain**:
   - Admin Portal -> Settings -> Domains -> Add domain -> Enter `acmecorp.com` -> Use this domain.
   - Log in to GoDaddy -> Add TXT record provided by Microsoft 365 -> Verify domain in Microsoft 365.

2. **Configure DNS Records**:
   - Admin Portal -> Settings -> Domains -> DNS settings.
   - Add MX, CNAME, TXT, and SRV records in GoDaddy as specified by Microsoft 365.
   - Confirm records in Microsoft 365 Admin Center.

3. **Validate Configuration**:
   - Send test emails, verify Autodiscover, and ensure Teams is working.

Confidence level: High

Source: [Microsoft 365 Admin Help Center](https://admin.microsoft.com)
