# Day 4 — Token errors (symptom → cause → fix)

1) token expired
- Cause: exp is in the past (or system clock wrong)
- Fix: re-auth / refresh token; check time sync

2) invalid_audience
- Cause: aud does not match the expected audience/client/api
- Fix: correct audience setting in IdP/app config

3) invalid_issuer
- Cause: iss does not match expected issuer URL
- Fix: use correct issuer/discovery URL and tenant config

4) insufficient_scope / forbidden
- Cause: token lacks required scopes/permissions
- Fix: request correct scopes; update app/IdP scope config

5) signature invalid
- Cause: token signed with wrong key or key rotated
- Fix: update JWKS / signing key configuration
