### 1. Simple Credential-Based Methods

- **Basic Authentication**: The client transmits a username and password encoded in Base64 within the authorization header of every request. Because it is only encoded and not encrypted, it is rarely used in modern production environments due to security risks if HTTPS is missing.
    
- **Digest Authentication**: Introduced to improve security over basic authentication, this method uses a challenge-response mechanism. The server sends a unique challenge, and the client generates a hashed response using the password, keeping the raw credentials from being exposed.
    

### 2. State-Based & Token-Based Management

- **Session Authentication**: Traditional approach for server-rendered web applications where the server stores session data and drops a session ID cookie into the browser. Scaling this becomes difficult as it requires central state storage across multiple servers.
    
- **API Keys**: A unique, static identifier assigned to an application or developer. These typically authenticate the application itself (such as weather or maps integrations) rather than the individual user.
    
- **Bearer Tokens**: A stateless concept where whoever "bears" or holds the token is granted access. It uses the `Authorization: Bearer <token>` header format.
    
- **JSON Web Tokens (JWT)**: A specific structured token format containing user information in a signed JSON payload. Because they are digitally signed, servers can verify them without checking a database every time, making them excellent for microservices.
    
- **Access vs. Refresh Tokens**: Access tokens are short-lived credentials used to make API requests, limiting the damage window if compromised. Refresh tokens are longer-lived and used strictly to request a new access token without forcing user re-authentication.
    

### 3. Advanced Identity & Framework Protocols

- **OAuth 2.0**: An authorization framework that allows third-party applications to act on behalf of a user without seeing their actual password (e.g., granting a service access to your Google Drive). It focuses on _authorization_ (what you can access), not identity.
    
- **OpenID Connect (OIDC)**: An identity layer built directly on top of OAuth 2.0 that provides a standardized ID token containing verified user credentials to prove _authentication_ (who you are). This powers features like "Sign in with Google".
    
- **Single Sign-On (SSO)**: A unified user experience (often driven behind the scenes by OIDC or SAML) allowing a user to authenticate once to gain entry to an entire suite of company dashboards, emails, and tools.
    
