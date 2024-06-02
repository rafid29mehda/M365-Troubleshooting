To migrate from Google Workspace to Microsoft 365, you need to follow a comprehensive series of steps involving domain verification, user account setup, data migration, and verification. Here’s a detailed, step-by-step guide with scenarios and examples.

## Scenario: Acme Corporation Migration from Google Workspace to Microsoft 365

#### Step 1: Pre-Migration Preparation

**Objective**: Ensure that the domain is verified, user accounts are created in Microsoft 365, and admin access is granted in Google Workspace.

##### 1. Verify Domains

**Example**: Acme Corporation needs to verify `acmecorp.com` in Microsoft 365.

**Steps**:
1. **Log into Microsoft 365 Admin Center**:
   - Go to [admin.microsoft.com](https://admin.microsoft.com).
   - Sign in with your admin credentials.

2. **Add and Verify Domain**:
   - Navigate to `Settings` > `Domains`.
   - Click `Add domain`.
   - Enter `acmecorp.com` and click `Use this domain`.

3. **Follow Verification Instructions**:
   - Microsoft will provide a TXT record.
   - Log into your domain registrar (e.g., GoDaddy, Namecheap).
   - Add the TXT record to your DNS settings.
   - Go back to Microsoft 365 Admin Center and click `Verify`.

**Example Steps**:
```plaintext
Admin Portal -> Settings -> Domains -> Add domain -> Enter acmecorp.com -> Use this domain.
Follow verification instructions provided by Microsoft.
```

##### 2. Create User Accounts in Microsoft 365

**Example**: Create accounts for `john.doe@acmecorp.com` and `jane.smith@acmecorp.com`.

**Steps**:
1. **Navigate to Users Section**:
   - In the Microsoft 365 Admin Center, go to `Users` > `Active users`.
   - Click `Add a user`.

2. **Enter User Details**:
   - Fill in the required information (e.g., First name: John, Last name: Doe, Email: john.doe@acmecorp.com).
   - Repeat the process for Jane Smith.

**Example Steps**:
```plaintext
Admin Portal -> Users -> Active users -> Add a user -> Enter details for John Doe and Jane Smith.
```

##### 3. Grant Admin Access in Google Workspace

**Objective**: Ensure administrative access to all data in Google Workspace.

**Steps**:
1. **Log into Google Admin Console**:
   - Go to [admin.google.com](https://admin.google.com).
   - Sign in with your Super Admin account.

2. **Check Admin Privileges**:
   - Navigate to `Admin roles`.
   - Ensure your account has Super Admin privileges.

**Example Steps**:
```plaintext
Google Admin Console -> Admin roles -> Ensure your account is a Super Admin.
```

#### Step 2: Use Microsoft 365 Migration Tool

**Objective**: Prepare Microsoft 365 to connect to Google Workspace and migrate data.

##### 1. Set Up Migration

**Example**: Acme Corporation sets up migration for emails.

**Steps**:
1. **Navigate to Data Migration**:
   - In the Microsoft 365 Admin Center, go to `Setup` > `Data migration`.
   - Click on `Add new migration`.

2. **Select Migration Source**:
   - Choose `Gmail` as the migration source.
   - Enter Google Workspace admin credentials to authenticate.

**Example Steps**:
```plaintext
Admin Portal -> Setup -> Data migration -> Add new migration -> Select Gmail -> Enter Google admin credentials.
```

##### 2. Select Users for Migration

**Objective**: Choose users’ data to migrate.

**Steps**:
1. **Prepare CSV File**:
   - Create a CSV file with the email addresses of Google Workspace users and their corresponding Microsoft 365 accounts.

**CSV File Example**:
```csv
EmailAddress,UserName
john.doe@acmecorp.com,john.doe@acmecorp.onmicrosoft.com
jane.smith@acmecorp.com,jane.smith@acmecorp.onmicrosoft.com
```

2. **Upload CSV File**:
   - In the Data Migration wizard, upload the CSV file.

**Example Steps**:
```plaintext
Prepare CSV file with user mappings.
Admin Portal -> Setup -> Data migration -> Upload CSV file.
```

##### 3. Start the Migration

**Objective**: Begin the migration process.

**Steps**:
1. **Select Data Types**:
   - Choose the data types to migrate (email, calendar, contacts).
   - Click `Start migration`.

**Example Steps**:
```plaintext
Admin Portal -> Setup -> Data migration -> Select data types -> Start migration.
```

#### Step 3: Migrate Google Drive Data to OneDrive

**Objective**: Transfer files from Google Drive to OneDrive.

##### 1. Install Google Drive File Stream and OneDrive Sync Client

**Steps**:
1. **Download and Install Clients**:
   - Install Google Drive File Stream on users' computers.
   - Install OneDrive sync client on users' computers.

**Example Steps**:
```plaintext
Download and install Google Drive File Stream and OneDrive sync client.
```

##### 2. Move Files Manually or Use a Third-Party Tool

**Objective**: Transfer files efficiently.

**Steps**:
1. **Manual Transfer**:
   - Users drag and drop files from Google Drive File Stream folder to OneDrive sync folder.

2. **Third-Party Tool (Mover)**:
   - Configure source (Google Drive) and destination (OneDrive) in Mover.
   - Start migration.

**Example Steps**:
```plaintext
Manual Transfer: Drag files from Google Drive to OneDrive.
OR
Mover: Configure source and destination -> Start migration.
```

#### Step 4: Migrate Google Calendar to Microsoft Outlook

**Objective**: Transfer calendar data.

##### 1. Export Google Calendar

**Steps**:
1. **Export Calendar Data**:
   - In Google Calendar, go to `Settings` > `Import & Export`.
   - Click `Export` and download the .ics file.

**Example Steps**:
```plaintext
Google Calendar -> Settings -> Import & Export -> Export -> Download .ics file.
```

##### 2. Import Calendar to Microsoft Outlook

**Steps**:
1. **Import .ics File**:
   - Open Microsoft Outlook.
   - Go to `File` > `Open & Export` > `Import/Export`.
   - Choose `Import an iCalendar (.ics) or vCalendar file`, and select the downloaded .ics file.

**Example Steps**:
```plaintext
Outlook -> File -> Open & Export -> Import/Export -> Import an iCalendar (.ics) file -> Select .ics file.
```

#### Step 5: Migrate Google Contacts to Microsoft 365

**Objective**: Transfer contacts.

##### 1. Export Google Contacts

**Steps**:
1. **Export Contacts Data**:
   - In Google Contacts, go to `More` > `Export`.
   - Select `Google CSV` format and export.

**Example Steps**:
```plaintext
Google Contacts -> More -> Export -> Select Google CSV format -> Export.
```

##### 2. Import Contacts to Microsoft 365

**Steps**:
1. **Import CSV File**:
   - In Outlook, go to `File` > `Open & Export` > `Import/Export`.
   - Choose `Import from another program or file`, select `Comma Separated Values`, and import the CSV file.

**Example Steps**:
```plaintext
Outlook -> File -> Open & Export -> Import/Export -> Import from another program or file -> Select CSV file.
```

### Conclusion

By following these detailed steps, you can ensure a smooth and successful migration from Google Workspace to Microsoft 365. It is advisable to test each step with a few accounts before performing a full-scale migration to identify and resolve any potential issues.

Confidence level: High

Source: [Microsoft - Migrate from G Suite](https://docs.microsoft.com/en-us/exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)
