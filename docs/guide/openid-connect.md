# OpenID Connect Authentication

OpenID Connect integration allows users to authenticate using external identity providers like Azure AD, Google, Okta, Keycloak, or Dex. This enables single sign-on (SSO) capabilities and
centralized identity management.

## Configuration

OpenID Connect authentication is configured through the `appsettings.json` file:

  ```json
  {
    "OpenIdConnect": {
      "Enabled": true,
      "ClientId": "cervantes",
      "Authority": "https://your-oidc-provider.com",
      "ClientSecret": "your-client-secret"
    }
  }
```

## Configuration Parameters

  | Parameter    | Description                                                   | Required |
  |--------------|---------------------------------------------------------------|----------|
  | Enabled      | Enable/disable OpenID Connect authentication                  | Yes      |
  | ClientId     | Client identifier registered with the OpenID Connect provider | Yes      |
  | Authority    | The base URL of the OpenID Connect provider                   | Yes      |
  | ClientSecret | Client secret for authentication                              | Yes      |

## Provider Examples

### Keycloak
```json
  {
    "OpenIdConnect": {
      "Enabled": true,
      "ClientId": "cervantes",
      "Authority": "https://your-keycloak-server.com/auth/realms/your-realm",
      "ClientSecret": "your-keycloak-client-secret"
    }
  }
```

### Dex (Development)

```json
  {
    "OpenIdConnect": {
      "Enabled": true,
      "ClientId": "cervantes",
      "Authority": "http://127.0.0.1:5556/dex",
      "ClientSecret": "cervantes"
    }
  }
```
## User Management

  **Important:** Pre-existing Users Required

  OpenID Connect authentication requires users to already exist in the Cervantes system. The system does not automatically create new users from OpenID Connect claims.

### User Association Process

  1. User authenticates with OpenID Connect provider
  2. Provider returns user claims (including email)
  3. Cervantes searches for existing user by email address
  4. If user exists, creates external login association
  5. User is signed into Cervantes with their existing roles

### Creating Users for OpenID Connect

  Before users can authenticate via OpenID Connect:

  1. Admin creates user account in Cervantes
  2. Email address must match the email claim from OpenID Connect provider
  3. Assign appropriate roles (User, Manager, Admin)
  4. User can then authenticate via OpenID Connect

## Troubleshooting

  ### Common Issues

  1. User not found error
    - Ensure user exists in Cervantes system
    - Verify email addresses match exactly
    - Check user account is active
  2. Invalid redirect URI
    - Verify callback URL configuration
    - Check for HTTPS vs HTTP mismatch
    - Ensure exact URL match with provider
  3. Authentication failed
    - Verify client ID and secret
    - Check authority URL is correct
    - Ensure required scopes are requested

### Debug Information

  Check application logs for:
  - External login attempts
  - User matching errors
  - OpenID Connect provider responses
  - Authentication failures

### Test Configuration

  1. Enable OpenID Connect in configuration
  2. Create test user with known email
  3. Test authentication flow
  4. Verify user roles and permissions

### Limitations

  Current Implementation Limitations

  - No automatic user provisioning: Users must exist before authentication
  - Email-only matching: User association based solely on email claim
  - No group mapping: OpenID Connect groups not mapped to Cervantes roles
  - Single claim mapping: Only email claim is processed

## Best Practices

### User Management

  - Create users before enabling OpenID Connect access
  - Use consistent email addresses across systems
  - Regularly audit external login associations
  - Document provider-specific configurations

### Security

  - Rotate client secrets regularly
  - Use secure storage for sensitive configuration
  - Monitor authentication patterns for anomalies
  - Implement proper logout procedures

### Testing

  - Test with multiple providers if applicable
  - Verify role assignments work correctly
  - Test error scenarios (user not found, etc.)
  - Validate callback URL configurations