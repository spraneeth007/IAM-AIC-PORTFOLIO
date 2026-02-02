# Day 4 — JWT + ID token vs Access token

## JWT (JSON Web Token)
A signed token with 3 parts:
- header
- payload (claims)
- signature

If the signature is valid, the token wasn't tampered with.

## Key claims
- iss (issuer): who issued the token
- aud (audience): who the token is intended for
- exp (expiry): when it expires
- sub (subject): user id
- scope: permissions (commonly in access tokens)

## ID token (OIDC)
- Purpose: proves who the user is (authentication result)
- Used by: the client application
- Think: identity card

## Access token (OAuth2)
- Purpose: allows access to APIs/resources (authorization)
- Used by: resource servers/APIs
- Think: permission pass
