---
name: hm-security-auth
description: Authentication and API security checklists. Use when implementing auth, login, registration, or reviewing security.
license: MIT
compatibility: codex
---

[Authentication Security Checklist]

Passwords hashed with bcrypt or argon2 (minimum 12 rounds)
Tokens stored in httpOnly cookies — not localStorage
JWT secret is random, at least 32 characters, not from a tutorial
Access tokens expire (15 to 60 minutes max)
Refresh token rotation implemented
Rate limiting on /login and /register
Account lockout after repeated failures
Sessions invalidated server-side on logout
Email verification required before access granted

[API Security Checklist]

Every route verified for authentication (check all endpoints, not just obvious ones)
Authorization checked: each user can only access their own data
All request inputs validated with schema validation (Zod, Joi, etc.)
API responses never include passwords, hashes, or internal fields
Error messages don't reveal system internals or file paths
Rate limiting on all public-facing endpoints
CORS restricted to your domain (not wildcard *)
HTTPS enforced, HTTP redirected

[Database Security Checklist]

No SQL string concatenation (use parameterized queries or ORM)
Application uses a limited-permission DB user, not root
Database not publicly accessible (behind VPC or firewall rule)
Backups configured and restore has been tested (not just backup)
Sensitive fields encrypted at rest

[Infrastructure Security Checklist]

All secrets in environment variables, not source code
.env not in git history (run: git log -- .env)
SSL certificate installed and valid
Server not running as root user
Only ports 80 and 443 publicly accessible

[Code Security Checklist]

No console.log statements in production build
`npm audit` run, all critical vulnerabilities resolved
No hardcoded credentials anywhere in the codebase
