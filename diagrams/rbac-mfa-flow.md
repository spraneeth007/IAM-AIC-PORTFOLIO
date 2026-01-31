# RBAC + MFA Flow (IAM Engineer view)

## RBAC (Role-Based Access Control)
- Roles: Admin, Manager, Employee
- Permissions are attached to roles
- Users get access by being assigned a role (often via groups)

## MFA (Multi-Factor Authentication)
- Something you know: password
- Something you have: phone/OTP
- Something you are: biometrics

## Combined flow (simple)
1) User tries to access App
2) System authenticates user (password)
3) System checks policy:
   - If risk is high OR role is sensitive → require MFA
4) User completes MFA
5) Authorization decision:
   - If user role allows resource → Allow
   - Else → Deny

## How to talk about it (60 seconds)
"RBAC controls what a user can do after login by mapping users to roles and roles to permissions. MFA strengthens authentication, especially for high-risk logins or privileged roles. As an IAM engineer, I configure both: the authentication journey and the authorization policy."
