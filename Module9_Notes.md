# Module 9: Access Control and Password Management

## Access Control

### Key Terms & Principles

- Access control scope - access control touches many areas of IT
- Data Owner - the creator and primary stake holder of a category of information
- Data Custodian - the administrator responsible for managing access

### Data Classification by Sensitivity and by Type

- Two primary categories, information cleared for release to the public and all else
- Data classification is the responsibility of the data owner

### Identity, Authentication, Authorization, and Accountability

### Controlling Access

- Least Privilege
- Need to Know
- Need to Know
- Rotation of Duties

### Access Control Techniques

- Discretionary (DAC): Managed by users
- Mandatory (MAC): Requires matching classification and clearance for access
- Role-based (RBAC): Based on group membership
- Ruleset-based (RSBAC): Rules for a specific object (ex.firewall rules)
- List-based: List of permitted users for each object
- Token-based: List of permitted objects for each user

### Managing Access

- Account Administration uses best-practice recommendations to only setup accounts for people who require them
- Maintenance includes reviewing account data for errors and inconsistencies
- Monitoring includes auditing access authorizations and failures
- Revocation includes the removal of access when necessary

### Single Sign-On (SSO)

- Only have to log on once
- Credentials are carried with the user
- Simplifies user management
- Allow centralized management
- Only have to remember one set of credentiaIs

### Protocols and Centralized Control

- Password Authentication Protocol (PAP)
- Challenge Handshake Authentication Protocol (CHAP)

## Password Management

- Reversible and Irreversible Encryption
- Access Control: Passwords

### Password management technologies

### What Determines the Strength of a Password Hash?

- Quality of algorithm 
- Key length 
- CPU cycles 
- Character set support 
- Password length

### Methods of Password Assessment

- Dictionary attack
- Hybrid attack
-  Brute force attack
- Precomputation brute force attack (rainbow tables)
- Brute force should only be used to recover lost passwords
-  Quality of passwords is an indicator of Security Posture

### Password cracking and countermeasures

- John the Ripper
- cain
- Rainbow Tables

### Windows Passwords

- All passwords are crackable
- Microsoft's design just makes it easier

### How to Protect Against Password Cracking Attacks

- Enforce a strong password policy
- Use shadow passwords (Unix)
-  Use one-time passwords
- Use passwd + to enforce strong passwords
- Disable LANMAN
- Fighting pre-computation attacks
-  Protect the encrypted passwords

### Enforce a Strong Password Policy

### Use Shadow Passwords - Unix system

- /etc/passwd, /etc/shadow

### Use One-time Passwords

- smart cards/tokens
- S/KEY
- Biometrics

### Utilize Biometrics（各种生物特征）

- 独一无二性

### Disabling LAN Manager Authentication