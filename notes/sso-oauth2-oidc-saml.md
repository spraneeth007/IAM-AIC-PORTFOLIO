# Day 3 — SSO, OAuth2, OIDC, SAML (simple)

## SSO (Single Sign-On) = the goal
SSO means: user logs in once with an Identity Provider (IdP) and then can access multiple apps without logging in again.
Why companies use it:
- fewer passwords
- central control (disable 1 account disables access everywhere)
- enforce MFA consistently

## OAuth2 = authorization (permission), NOT login
OAuth2 helps an app access a protected resource (usually an API) with permission, without sharing user passwords.

Key actors:
- Resource Owner: user
- Client: application
- Authorization Server: issues tokens
- Resource Server: API

Output: Access token (permission to access API)

## OIDC = login/identity built on OAuth2
OIDC adds authentication to OAuth2.
Key addition: ID Token (usually a JWT) that represents the user identity.

OIDC outputs:
- ID Token = who the user is (identity)
- Access Token = permission to call APIs (authorization)

OIDC common flow (Auth Code + PKCE):
1) User opens app
2) App redirects user to IdP login
3) User logs in at IdP
4) IdP returns an authorization code to the app
5) App exchanges code for tokens (ID token + access token)
6) App creates a session (cookie/session) so user stays logged in

PKCE: protects against stolen authorization codes being reused.

## SAML = enterprise SSO using signed assertions (XML)
SAML uses a signed XML assertion to tell the Service Provider (SP/app) that the user authenticated at the Identity Provider (IdP).

SAML flow:
1) User opens SP (app)
2) SP redirects to IdP
3) User logs in
4) IdP sends signed SAML assertion back to SP
5) SP creates a session

## OIDC vs SAML (what I use in implementation)
- Prefer OIDC for modern web/mobile/API apps
- Use SAML when the app only supports SAML or enterprise SaaS requires it

Quick comparison:
- OIDC: JWT/JSON tokens, redirect URIs, scopes/claims
- SAML: XML assertions, metadata, ACS URLs, certificates, attributes/NameID
