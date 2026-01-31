# Authentication vs Authorization (Simple)

## Authentication = "Who are you?"
Examples:
- Password login
- OTP
- Biometrics
Output: the system is confident about your identity

## Authorization = "What are you allowed to do?"
Examples:
- Can you view payroll?
- Can you access admin dashboard?
- Can you approve refunds?
Output: allow/deny decision

## IAM Engineer interview line (short)
"Authentication proves identity. Authorization decides permissions. In IAM, we design both the login flow (auth) and access policies (authz)."

## Common real-world failure
- User can log in but gets "Access Denied"
Likely cause:
- Role/group missing OR policy misconfigured OR wrong attribute mapping
What to check:
- User group membership
- role mapping rules
- policy evaluation logs
