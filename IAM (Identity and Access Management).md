# IAM (Identity and Access Management)

IAM is a **global AWS service** used to manage users and permissions.

- **Important Points**
  - Root account is created by default.
  - Root account **should not be used for daily tasks**.
  - Users and groups are assigned **JSON policies**.
  - Policies define **permissions**.

AWS follows the **Least Privilege Principle**:

> Give users only the permissions they need.

### IAM Policy Document Structure

    - Example IAM policy structure:

```json
{
  "Version": "2012-10-17",
  "Id": "S3-ID",
  "Statement": [
    {
      "Sid": "Statement1",
      "Effect": "Allow",
      "Principal": {
        "AWS": []
      },
      "Action": [],
      "Resource": []
    }
  ]
}
```

#### Policy Elements

| Field     | Description                      |
| --------- | -------------------------------- |
| Version   | Policy language version          |
| Id        | Policy identifier                |
| Statement | Defines permissions              |
| Sid       | Statement identifier             |
| Effect    | Allow or Deny                    |
| Action    | AWS service actions              |
| Resource  | Resources affected by the policy |

### IAM Password Policy

Strong password policies improve security.

- **Configuration Options**
  - Minimum password length
  - Required character types
  - Allow users to change their password
  - Password expiration
  - Prevent password reuse

### Multi-Factor Authentication (MFA)

- **MFA requires**:
  - Password
  - Security device

- **MFA Device Options**:
  - Virtual MFA (Google Authenticator)
  - U2F Security Key (Yubikey)
  - Hardware Key Fob

### AWS GovCloud (US)

A special AWS region designed for **US government workloads requiring strict compliance**.

### How Users Access AWS

1. AWS Management Console (Web UI, MFA supported)
2. AWS CLI (Command Line Interface)
3. AWS SDK (Programming language integration)

Authentication for CLI and SDK uses **Access Keys**.

### AWS CLI / AWS CloudShell

Used to **manage AWS services from the command line**.

## IAM Roles

IAM Roles allow **AWS services to access other AWS services securely**.

Example:

- EC2 accessing S3

### IAM Security Tools

1. IAM Credentials Report
   - Account-level report listing:
     - Users
     - Password status
     - Access keys
     - MFA usage

2. IAM Access Advisor / Last Accessed
   - Shows:
     - When a user last accessed a service
     - Which services were used

### IAM Best Practices

1. Do not use root account except for setup
2. One physical user = One IAM user
3. Assign permissions to groups
4. Create strong password policy
5. Enable MFA
6. Use IAM roles for AWS services
7. Audit permissions using credential reports
8. Never share access keys

### IAM Summary

- **Users** – Individual AWS identities
- **Groups** – Collection of users
- **Policies** – JSON permissions document
- **Roles** – Used by AWS services
- **Security** – MFA + Password policy
- **Access Keys** – Used for CLI / SDK
- **Audit** – Credential Reports & Access Advisor

---
