Title: OIDC Auth Code + PKCE (Simple Flow)

Actors:

User (browser)

App (client)

Identity Provider (IdP)

Steps:

User opens App

App redirects user to IdP login page

User logs in at IdP

IdP sends authorization code back to App (via redirect)

App exchanges code for tokens:

ID token (who the user is)

Access token (permission to call APIs)

App creates session for user

PKCE (why):

prevents stolen authorization code from being reused by attacker

Common failures

redirect URI mismatch

wrong client id/secret

code expired

token audience/issuer mismatch