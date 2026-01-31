Title: Top SSO Issues (Symptoms → Cause → Fix)

“Invalid redirect_uri”

Cause: redirect URI in app doesn’t match IdP config

Fix: update redirect URI in IdP client settings

“Login loop”

Cause: cookie blocked / SameSite issue / session not stored

Fix: check cookie flags, browser settings, session configuration

“invalid_client”

Cause: wrong client id/secret

Fix: update credentials in app

“invalid_audience” / “invalid_issuer”

Cause: token claims don’t match what app expects

Fix: correct issuer/audience settings; verify discovery URL

“SAML response rejected”

Cause: certificate mismatch / expired cert

Fix: update cert and metadata on SP/IdP

“Clock skew”

Cause: time mismatch → assertion/token appears expired

Fix: sync NTP/time on servers