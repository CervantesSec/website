# LDAP Authentication

The LDAP authentication feature allows organizations to integrate their existing LDAP directory services with Cervantes, enabling single sign-on capabilities and centralized user management.

## Configuration

LDAP authentication is configured through the `appsettings.json` file. Here's an example configuration:

  ```json
  {
    "LdapConfiguration": {
      "Enabled": true,
      "Server": "ldap.company.com",
      "Port": 389,
      "UseSSL": false,
      "BaseDN": "dc=company,dc=com",
      "UserDN": "ou=users,dc=company,dc=com",
      "UserSearchFilter": "(uid={0})",
      "GroupSearchBase": "ou=groups,dc=company,dc=com",
      "GroupSearchFilter": "(&(objectClass=groupOfNames)(member={0}))",
      "AdminUsername": "cn=admin,dc=company,dc=com",
      "AdminPassword": "your_admin_password",
      "UserAttribute": "uid",
      "EmailAttribute": "mail",
      "DisplayNameAttribute": "cn",
      "FirstNameAttribute": "givenName",
      "LastNameAttribute": "sn",
      "DefaultRole": "User",
      "GroupRoleMapping": {
        "IT-Admins": "Admin",
        "Security-Team": "Admin",
        "Pentesting-Team": "User",
        "Developers": "User",
        "Managers": "User"
      }
    }
  }
```

### Configuration Parameters

  | Parameter            | Description                                             | Required |
  |----------------------|---------------------------------------------------------|----------|
  | Enabled              | Enable/disable LDAP authentication                      | Yes      |
  | Server               | LDAP server hostname or IP address                      | Yes      |
  | Port                 | LDAP server port (usually 389 for non-SSL, 636 for SSL) | Yes      |
  | UseSSL               | Whether to use SSL/TLS encryption                       | Yes      |
  | BaseDN               | Base Distinguished Name for LDAP searches               | Yes      |
  | UserDN               | Distinguished Name for user searches                    | Yes      |
  | UserSearchFilter     | LDAP filter for finding users                           | Yes      |
  | GroupSearchBase      | Base DN for group searches                              | No       |
  | GroupSearchFilter    | LDAP filter for finding user groups                     | No       |
  | AdminUsername        | LDAP admin username for binding                         | Yes      |
  | AdminPassword        | LDAP admin password for binding                         | Yes      |
  | UserAttribute        | LDAP attribute containing username                      | Yes      |
  | EmailAttribute       | LDAP attribute containing email address                 | Yes      |
  | DisplayNameAttribute | LDAP attribute for display name                         | No       |
  | FirstNameAttribute   | LDAP attribute for first name                           | No       |
  | LastNameAttribute    | LDAP attribute for last name                            | No       |
  | DefaultRole          | Default role assigned to new LDAP users                 | Yes      |
  | GroupRoleMapping     | Mapping of LDAP groups to Cervantes roles               | No       |

### User Experience

  When LDAP authentication is enabled, users will see an "LDAP Login" option on the login page. Users can authenticate using their LDAP credentials, and the system will automatically:

  1. Validate credentials against the LDAP directory
  2. Create a new user account if it doesn't exist
  3. Assign appropriate roles based on LDAP group membership
  4. Mark the user as an external user
  5. Sign the user into Cervantes

### Role Mapping

  The system supports automatic role assignment based on LDAP group membership. Configure the GroupRoleMapping section to map your LDAP groups to Cervantes roles:

  - Admin: Full system access
  - User: Standard user access

  If a user doesn't belong to any mapped groups, they will be assigned the DefaultRole.

### Security Considerations

  - Store LDAP admin credentials securely
  - Use SSL/TLS encryption in production environments
  - Regularly review and update group mappings
  - Monitor LDAP authentication logs for security events

### Troubleshooting

#### Common Issues

  1. Connection refused: Check server hostname, port, and network connectivity
  2. Authentication failed: Verify admin credentials and user search filters
  3. No email found: Ensure the email attribute is correctly configured
  4. Role assignment issues: Check group search configuration and mappings

#### Logs

  LDAP authentication events are logged with the following prefixes:
  - LDAP Login successful: Successful authentication
  - LDAP Login failed: Authentication failure
  - LDAP Error: System errors during authentication

  Check the application logs for detailed error messages when troubleshooting LDAP issues.

