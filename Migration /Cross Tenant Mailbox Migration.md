Cross-tenant mailbox migration in Microsoft 365 involves moving mailboxes from one Microsoft 365 tenant to another. This process is often needed during mergers, acquisitions, or company rebranding. Here’s a detailed guide with steps and an example:

## Step-by-Step Guide for Cross-Tenant Mailbox Migration

1. **Pre-Migration Preparation**
   - **Domain Verification**: Verify that both source and target tenants have appropriate admin permissions.
   - **Global Admin Access**: Ensure you have global admin access in both tenants.
   - **Prepare Source Tenant**: Ensure no legal holds or compliance holds are in place that might prevent migration.
   - **Prepare Target Tenant**: Ensure licenses are available in the target tenant for the users being migrated.

2. **Configure Azure AD Applications**
   - **Register Azure AD Applications**: Register Azure AD applications in both source and target tenants.
   - **Assign Permissions**: Assign the required permissions (Mail.ReadWrite, User.Read) to these applications.

3. **Establish Trust Between Tenants**
   - **Create Migration Endpoint**: In the target tenant, create a migration endpoint that connects to the source tenant.
   - **App Permissions**: Establish application permissions and trust using OAuth tokens between the source and target Azure AD applications.

4. **Prepare Mailboxes for Migration**
   - **Generate a List**: Export a list of mailboxes to be migrated from the source tenant.
   - **Map Mailboxes**: Map each source mailbox to the corresponding target mailbox.

5. **Migration Batch Creation**
   - **Create Migration Batches**: Using the Exchange Admin Center or PowerShell, create migration batches that specify which mailboxes to migrate.
   - **Start Migration**: Start the migration batches and monitor the progress.

6. **Post-Migration Tasks**
   - **Verify Mailbox Migration**: Ensure all data has been migrated correctly by checking the mailboxes in the target tenant.
   - **Update DNS Records**: Update MX and other DNS records to point to the target tenant.
   - **Decommission Old Environment**: Once confirmed, decommission mailboxes in the source tenant if no longer needed.

## Example

This guide will cover the detailed steps required for a cross-tenant mailbox migration in Microsoft 365, from verifying domains to completing the migration. Each step is illustrated with an example.

#### Example Scenario
- **Source Tenant**: `sourcecompany.onmicrosoft.com`
- **Target Tenant**: `targetcompany.onmicrosoft.com`
- **User to Migrate**: `user@sourcecompany.com` to `user@targetcompany.com`

### Step-by-Step Guide

#### Step 1: Pre-Migration Preparation

1. **Verify Domains**

   **Objective**: Ensure both source and target tenants have verified domains.

   **Steps**:
   - **Log into Microsoft 365 Admin Center** for both tenants.

     **Source Tenant Verification**:
     1. Go to `admin.microsoft.com`.
     2. Navigate to `Settings` > `Domains`.
     3. Ensure `sourcecompany.onmicrosoft.com` is listed and verified.

     **Target Tenant Verification**:
     1. Repeat the same steps for `targetcompany.onmicrosoft.com`.

   **Example**:
   ```plaintext
   Admin Portal -> Settings -> Domains
   - Ensure 'sourcecompany.onmicrosoft.com' is verified in Source Tenant.
   - Ensure 'targetcompany.onmicrosoft.com' is verified in Target Tenant.
   ```

2. **Ensure Global Admin Accounts**

   **Objective**: Confirm that you have global admin access in both tenants.

   **Steps**:
   - **Check Admin Role**:
     1. Go to `admin.microsoft.com`.
     2. Navigate to `Users` > `Active Users`.
     3. Select your account and click on `Manage Roles`.
     4. Ensure `Global Admin` is checked.

   **Example**:
   ```plaintext
   Admin Portal -> Users -> Active Users -> Select Your User -> Manage Roles -> Ensure 'Global Admin' is checked.
   ```

#### Step 2: Configure Azure AD Applications

1. **Register Azure AD Applications**

   **Objective**: Create and configure Azure AD applications in both source and target tenants.

   **Steps**:
   - **Source Tenant**:
     1. Go to `portal.azure.com`.
     2. Navigate to `Azure Active Directory` > `App registrations` > `New registration`.
     3. Register an app named `SourceApp`.

   - **Target Tenant**:
     1. Repeat the same steps for the target tenant, registering an app named `TargetApp`.

   **Example**:
   ```plaintext
   Azure Portal -> Azure Active Directory -> App registrations -> New registration
   - Name: SourceApp (in Source Tenant)
   - Name: TargetApp (in Target Tenant)
   ```

2. **Assign Permissions**

   **Objective**: Assign the required API permissions to the Azure AD applications.

   **Steps**:
   - **Source and Target Tenant**:
     1. Go to `App registrations` > Select your app (`SourceApp` or `TargetApp`).
     2. Navigate to `API permissions` > `Add a permission`.
     3. Select `Microsoft Graph` and add `Mail.ReadWrite`, `User.Read`.
     4. Grant admin consent for the tenant.

   **Example**:
   ```plaintext
   Azure Portal -> App registrations -> Select App -> API permissions -> Add a permission -> Microsoft Graph
   - Permissions: Mail.ReadWrite, User.Read
   - Grant admin consent
   ```

#### Step 3: Establish Trust Between Tenants

1. **Create Migration Endpoint**

   **Objective**: Set up a migration endpoint in the target tenant to connect to the source tenant.

   **Steps**:
   - **In Target Tenant**:
     1. Go to `admin.exchange.microsoft.com`.
     2. Navigate to `Recipients` > `Migration` > `Endpoints`.
     3. Click `New` to create a migration endpoint.
     4. Use the source tenant admin credentials to configure the endpoint.

   **Example**:
   ```plaintext
   Exchange Admin Center (Target Tenant) -> Recipients -> Migration -> Endpoints -> New
   - Use Source Tenant Admin Credentials
   ```

2. **App Permissions and Trust**

   **Objective**: Set up OAuth tokens and permissions between the source and target Azure AD applications.

   **Steps**:
   - **Obtain OAuth Tokens**:
     1. In both tenants, navigate to `App registrations` > `Certificates & secrets`.
     2. Generate a new client secret and note the client ID and secret.
     3. Exchange these tokens between the source and target apps.

   **Example**:
   ```plaintext
   Azure Portal -> App registrations -> Select App -> Certificates & secrets
   - Generate client secret
   - Note Client ID and Secret
   - Exchange tokens between SourceApp and TargetApp
   ```

#### Step 4: Prepare Mailboxes for Migration

1. **Generate a List of Mailboxes**

   **Objective**: Export the list of mailboxes to be migrated.

   **Steps**:
   - **Source Tenant**:
     1. Use PowerShell to export mailbox list:
        ```powershell
        Get-Mailbox -ResultSize Unlimited | Select-Object PrimarySmtpAddress | Export-Csv C:\mailboxes.csv -NoTypeInformation
        ```

   **Example**:
   ```powershell
   Get-Mailbox -ResultSize Unlimited | Select-Object PrimarySmtpAddress | Export-Csv C:\mailboxes.csv -NoTypeInformation
   ```

2. **Map Mailboxes**

   **Objective**: Create a mapping file for source and target mailboxes.

   **Steps**:
   - **Create CSV File**:
     ```csv
     SourceEmail,TargetEmail
     user@sourcecompany.com,user@targetcompany.com
     ```

#### Step 5: Migration Batch Creation

1. **Create Migration Batches**

   **Objective**: Create and start migration batches.

   **Steps**:
   - **Using PowerShell**:
     ```powershell
     New-MigrationBatch -Name "Batch1" -SourceEndpoint "MigrationEndpoint" -CSVData (Get-Content C:\mailboxes.csv | Out-String) -TargetDeliveryDomain "targetcompany.onmicrosoft.com" -AutoStart
     ```

   **Example**:
   ```powershell
   New-MigrationBatch -Name "Batch1" -SourceEndpoint "MigrationEndpoint" -CSVData (Get-Content C:\mailboxes.csv | Out-String) -TargetDeliveryDomain "targetcompany.onmicrosoft.com" -AutoStart
   ```

2. **Start Migration Batch**

   **Objective**: Start the created migration batch.

   **Steps**:
   - **Using PowerShell**:
     ```powershell
     Start-MigrationBatch -Identity "Batch1"
     ```

   **Example**:
   ```powershell
   Start-MigrationBatch -Identity "Batch1"
   ```

#### Step 6: Post-Migration Tasks

1. **Verify Mailbox Migration**

   **Objective**: Confirm that mailboxes have been migrated successfully.

   **Steps**:
   - **Using PowerShell**:
     ```powershell
     Get-MigrationBatch -Identity "Batch1" | Get-MigrationUser
     ```

   **Example**:
   ```powershell
   Get-MigrationBatch -Identity "Batch1" | Get-MigrationUser
   ```

2. **Update DNS Records**

   **Objective**: Update DNS records to point to the target tenant’s mail servers.

   **Steps**:
   - **DNS Management**:
     1. Log into your DNS provider’s management console.
     2. Update the MX records to point to `targetcompany.onmicrosoft.com`.

   **Example**:
   ```plaintext
   DNS Provider Console -> Update MX Records to 'targetcompany.onmicrosoft.com'
   ```

3. **Decommission Old Environment**

   **Objective**: Decommission the source tenant’s mailboxes if no longer needed.

   **Steps**:
   - **Remove Mailboxes**:
     1. Use PowerShell or the Exchange Admin Center to remove the old mailboxes from the source tenant.

   **Example**:
   ```powershell
   Remove-Mailbox -Identity user@sourcecompany.com
   ```

### Conclusion

Following these detailed steps ensures a smooth transition of mailboxes from one Microsoft 365 tenant to another. Always test with a small batch before proceeding with a full-scale migration to minimize disruptions.

Source: [Microsoft - Perform a cross-tenant mailbox migration](https://learn.microsoft.com/en-us/microsoft-365/enterprise/cross-tenant-mailbox-migration?view=o365-worldwide)
