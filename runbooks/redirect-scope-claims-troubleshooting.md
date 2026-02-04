# Day 5 — Integration troubleshooting: redirect, scopes, claims

1) invalid_redirect_uri
- Cause: callback URL mismatch (scheme/domain/path)
- Fix: add exact redirect URI in IdP client settings

2) missing email / name claim
- Cause: scope not requested OR claim not mapped
- Fix: request proper scopes (profile/email) and map attributes to claims

3) user logs in but app says "unauthorized"
- Cause: access token missing scope/role
- Fix: request correct scopes; configure authorization policy

4) login works in one environment but not another
- Cause: different redirect URI, issuer, audience, or client id per env
- Fix: verify per-environment configuration (dev/stage/prod)

5) works in browser, fails in API calls
- Cause: using ID token instead of access token for API
- Fix: send access token to API; validate aud/scope for that API
