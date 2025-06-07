# Security Models: Practical Application Questions 🛠️

## Practical Scenario Questions

### Question 1: RBAC Implementation
You are the security administrator for a financial institution. Design a basic RBAC structure for a banking application with the following requirements:
- Tellers can view account balances and process deposits/withdrawals
- Loan officers can process loan applications and view credit reports
- Branch managers can approve transactions over $10,000 and view employee records
- System administrators can manage user accounts but cannot access customer financial data

Create a table showing roles, permissions, and explain any hierarchical relationships.

**Sample Answer:**
```
Roles and Permissions:

1. Teller Role
   - View account balances
   - Process deposits
   - Process withdrawals up to $5,000
   
2. Loan Officer Role
   - View account balances
   - Process loan applications
   - Access credit reports
   - Schedule loan payments
   
3. Branch Manager Role (inherits Teller permissions)
   - Approve transactions over $10,000
   - Override holds on accounts
   - View employee performance records
   - Approve time-off requests
   
4. System Administrator Role
   - Create/modify user accounts
   - Reset passwords
   - Manage system configurations
   - View audit logs
```

Hierarchical relationship: Branch Manager inherits all Teller permissions plus has additional permissions. Loan Officer and System Administrator are separate roles with no inheritance.

Separation of Duty: System Administrators explicitly cannot access customer financial data, enforcing separation between system management and business functions.

### Question 2: Bell-LaPadula Scenario
A military organization uses the Bell-LaPadula model with four classification levels: Unclassified (1), Confidential (2), Secret (3), and Top Secret (4). For each of the following scenarios, indicate whether the access would be allowed or denied:

a) A user with Secret clearance attempts to read a Confidential document.
b) A user with Confidential clearance attempts to read a Secret document.
c) A user with Top Secret clearance attempts to write to a Secret document.
d) A user with Secret clearance attempts to write to a Top Secret document.
e) A user with Secret clearance attempts to write to an Unclassified document.

**Answer:**
a) Allowed - BLP allows reading at or below your clearance level (No Read Up)
b) Denied - Violates No Read Up (Confidential trying to read Secret)
c) Denied - Violates No Write Down (Top Secret writing to Secret)
d) Allowed - BLP allows writing at or above your clearance level
e) Denied - Violates No Write Down (Secret writing to Unclassified)

### Question 3: Chinese Wall Implementation
You are a security consultant for a large accounting firm that audits multiple companies in the same industries. Design a Chinese Wall implementation that:
1. Identifies at least three conflict of interest classes
2. Lists specific companies within each class
3. Explains how the system would track and enforce access restrictions
4. Describes what happens when an auditor attempts to access conflicting information

**Sample Answer:**

1. Conflict of Interest Classes:
   - Banking: Bank of America, Chase, Wells Fargo, Citibank
   - Telecommunications: AT&T, Verizon, T-Mobile, Sprint
   - Retail: Walmart, Target, Costco, Amazon

2. Implementation Approach:
   - Each auditor has an access history record
   - System checks this history before granting access to company data
   - Database maintains relationships between companies and their CoI classes

3. Enforcement Process:
   - When auditor requests access to Company X data:
     - System checks if auditor has previously accessed any company in same CoI class
     - If yes, system determines if it was Company X (allowed) or competitor (denied)
     - If no previous access in that CoI class, access is granted and recorded

4. Access Attempt Scenario:
   - Auditor Smith has previously accessed Bank of America data
   - Smith requests access to Chase data
   - System identifies both are in Banking CoI class
   - System denies access and logs attempt
   - System notification: "Access denied due to potential conflict of interest with previous work for Bank of America"

### Question 4: CISS Model Application
You are implementing a Clinical Information Systems Security model for a hospital. For each scenario below, determine if access should be granted, denied, or granted with special logging:

a) Dr. Johnson attempts to view medical records for a patient currently under her care
b) Nurse Smith attempts to view billing records for a patient on his ward
c) Dr. Williams attempts to view records for a patient she treated last year but is no longer treating
d) ER Doctor Garcia attempts to view records for an unconscious emergency patient just admitted
e) Dr. Johnson attempts to view records for a celebrity patient not under her care

**Answer:**
a) Granted - Treatment relationship exists
b) Denied - Nurses typically don't need billing record access (role mismatch)
c) Denied - No current treatment relationship
d) Granted with special logging - Emergency override justified for unconscious patient
e) Denied - No treatment relationship; accessing for curiosity violates need-to-know

### Question 5: ORCON Practical Application
You work for an intelligence agency that shares information with allied agencies using ORCON principles. Design a system that:
1. Allows document originators to specify authorized recipients
2. Prevents unauthorized redistribution
3. Handles requests for expanded access
4. Tracks all access to controlled documents

**Sample Answer:**

1. Document Control System:
   - Each document contains embedded metadata with:
     - Originator information
     - Authorized recipient list
     - Distribution restrictions
     - Expiration/review dates

2. Redistribution Prevention:
   - Documents are encrypted with keys controlled by originator
   - Viewing software enforces ORCON restrictions
   - Watermarking identifies specific authorized recipients
   - System prevents copying/printing without authorization

3. Access Request Handling:
   - Recipients can submit access expansion requests through the system
   - Requests automatically routed to document originator
   - Originator can approve/deny with single click
   - If approved, system automatically updates metadata and grants access

4. Tracking Implementation:
   - Comprehensive audit logging of all document access
   - Records who, when, where, and how long document was accessed
   - Periodic reports sent to originators showing access patterns
   - Automated alerts for unusual access patterns

## Hands-On Configuration Questions

### Question 6: RBAC Configuration
You need to implement RBAC in a Linux environment using sudo and user groups. Write the commands to:
1. Create a group for database administrators
2. Create a group for application developers
3. Add user 'jsmith' to the database administrators group
4. Configure sudo to allow database administrators to restart the database service without a password
5. Configure sudo to allow developers to restart the application service but require a password

**Answer:**
```bash
# 1. Create database administrators group
sudo groupadd dbadmins

# 2. Create application developers group
sudo groupadd developers

# 3. Add jsmith to database administrators
sudo usermod -aG dbadmins jsmith

# 4. Configure sudo for database administrators (no password)
echo "%dbadmins ALL=(ALL) NOPASSWD: /bin/systemctl restart mysql.service" | sudo tee -a /etc/sudoers.d/dbadmins

# 5. Configure sudo for developers (with password)
echo "%developers ALL=(ALL) PASSWD: /bin/systemctl restart application.service" | sudo tee -a /etc/sudoers.d/developers
```

### Question 7: Access Control Matrix
Create an access control matrix for a system with the following entities and requirements:
- Users: Alice, Bob, Charlie
- Files: ProjectPlan.doc, Budget.xls, SourceCode.zip
- Alice owns ProjectPlan.doc and can read/write it
- Bob owns Budget.xls and can read/write it
- Charlie owns SourceCode.zip and can read/write it
- Alice can read Budget.xls but not write to it
- Bob and Charlie can read ProjectPlan.doc but not write to it
- Only Charlie can read/write SourceCode.zip

**Answer:**
```
Access Control Matrix:

| Subject\Object | ProjectPlan.doc | Budget.xls | SourceCode.zip |
|----------------|-----------------|------------|----------------|
| Alice          | read, write, own| read       | -              |
| Bob            | read            | read, write, own | -        |
| Charlie        | read            | -          | read, write, own |
```

### Question 8: Biba Model Implementation
You are implementing the Biba Integrity Model for a financial system with three integrity levels:
- High: Core financial calculation modules
- Medium: Reporting and analysis tools
- Low: Data import utilities and user interfaces

For each of the following operations, state whether it would be allowed or denied under Biba rules:

a) A high-integrity calculation module reads data from the medium-integrity reporting database
b) A medium-integrity reporting tool writes data to the high-integrity financial database
c) A low-integrity import utility writes data to the medium-integrity reporting database
d) A high-integrity calculation module writes results to the low-integrity user interface
e) A medium-integrity reporting tool reads data from the low-integrity import database

**Answer:**
a) Denied - Violates "No Read Down" (High cannot read Medium)
b) Denied - Violates "No Write Up" (Medium cannot write to High)
c) Denied - Violates "No Write Up" (Low cannot write to Medium)
d) Allowed - High can write to Low (writing down is permitted)
e) Denied - Violates "No Read Down" (Medium cannot read Low)

### Question 9: Security Model Selection
For each of the following organizations, identify the MOST appropriate security model and explain why:

a) A law firm that represents multiple clients in the same industry
b) A nuclear power plant control system
c) A hospital electronic health record system
d) A military intelligence agency
e) A university's student information system

**Answer:**
a) Chinese Wall - Prevents conflicts of interest between competing clients in the same industry
b) Biba Integrity Model - Ensures high-integrity control systems aren't corrupted by lower-integrity inputs
c) Clinical Information Systems Security (CISS) Model - Handles patient-provider relationships and emergency access
d) Bell-LaPadula with ORCON - Protects classified information with strict confidentiality controls while maintaining originator control
e) RBAC - Provides appropriate access based on roles (student, faculty, administrator) without the complexity of other models

### Question 10: Implementing Separation of Duties
You are configuring a financial system that requires separation of duties. Design controls for the following processes:

a) Purchase requisition and approval
b) Payroll processing and approval
c) System administration and security auditing
d) Code development and deployment to production

**Sample Answer:**

a) Purchase Requisition and Approval:
   - Role 1: Requisition Creator - Can create purchase requests
   - Role 2: Requisition Approver - Can approve requests
   - Control: System prevents the same user from creating and approving the same request
   - Implementation: Database trigger checks user_id of creator ≠ user_id of approver

b) Payroll Processing and Approval:
   - Role 1: Payroll Processor - Can enter hours and calculate pay
   - Role 2: Payroll Approver - Can approve final payroll
   - Role 3: Payment Executor - Can execute bank transfers
   - Control: Three separate individuals must be involved in the process
   - Implementation: Workflow requires three different user signatures

c) System Administration and Security Auditing:
   - Role 1: System Administrator - Can configure systems
   - Role 2: Security Auditor - Can review logs and configurations
   - Control: Auditors cannot make changes; Admins cannot delete logs
   - Implementation: Read-only access for auditors; append-only logs for admins

d) Code Development and Deployment:
   - Role 1: Developer - Can write and commit code
   - Role 2: Code Reviewer - Can approve code changes
   - Role 3: Deployment Manager - Can push to production
   - Control: Developers cannot deploy their own code to production
   - Implementation: Version control permissions and deployment pipeline controls

---

These practical questions should help you apply the theoretical concepts to real-world scenarios. Good luck with your exam! 🍀