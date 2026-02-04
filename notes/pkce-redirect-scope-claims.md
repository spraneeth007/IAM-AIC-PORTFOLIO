# Day 5 — PKCE, Redirect URIs, Scopes & Claims

## PKCE (why it exists)
PKCE protects the Authorization Code flow from code interception.
- App creates a code_verifier (secret)
- App sends code_challenge to IdP
- After login, app gets authorization code
- App exchanges code + verifier for tokens
IdP checks verifier matches the original challenge.

## Redirect URI (why it breaks)
Redirect URI is the allowed callback URL for the app.
It must match exactly in IdP configuration.
Mismatch → invalid_redirect_uri and login fails.

## Scopes vs Claims vs Attributes
- Scope = what the app requests (openid, profile, email)
- Claim = fields inside tokens (sub, email, name, iss, aud, exp)
- Attributes = user profile data in identity store
Mapping converts attributes → claims → tokens/assertions.
