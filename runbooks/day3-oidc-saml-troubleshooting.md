# Day 3 — OIDC + SAML Troubleshooting (symptom → cause → fix)

## OIDC common failures
1) invalid_redirect_uri
- Cause: redirect URI in app does not exactly match IdP client config
- Fix: update redirect URI to exact match

2) invalid_client
- Cause: wrong client_id or client_secret
- Fix: update client credentials in the app

3) invalid_issuer / invalid_audience
- Cause: token claims (iss/aud) do not match what the app expects
- Fix: verify issuer URL, discovery URL, and audience/client settings

4) authorization code expired / reused
- Cause: code used too late or reused
- Fix: retry login; ensure code is exchanged once; check time sync

5) token expired
- Cause: exp is reached (or time mismatch)
- Fix: refresh token flow (if used) or re-auth; fix clock/time sync

## SAML common failures
1) SAML response rejected (signature/cert)
- Cause: certificate mismatch or expired signing cert
- Fix: update signing certificate and re-import metadata

2) wrong ACS URL
- Cause: IdP posts assertion to wrong endpoint
- Fix: correct ACS URL in IdP/SP config

3) clock skew / assertion expired
- Cause: timestamps not valid due to time mismatch
- Fix: sync time using NTP on systems

4) missing attribute / NameID mapping
- Cause: app expects email/NameID but IdP isn't sending it
- Fix: configure attribute mapping and verify assertion contents

## My debugging approach (engineer style)
1) Identify protocol (OIDC or SAML)
2) Reproduce and capture the exact error
3) Use browser network trace:
   - OIDC: look for /authorize, redirect_uri, scope=openid, code
   - SAML: look for SAMLRequest/SAMLResponse, RelayState
4) Check IdP logs
5) Validate config:
   - OIDC: redirect URIs, client creds, issuer/audience, claims
   - SAML: metadata, ACS URL, certs, timestamps, attributes
6) Fix → retest → document the fix here
