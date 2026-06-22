# Checklist A1 — Security
# OWASP ASVS 5.0 Level 2 — filtered by project stack
#
# HOW TO USE THIS FILE
# --------------------
# 1. For each item, set STATUS to one of:
#    ✅ PASS | ❌ FAIL | ⚠️ PARTIAL | ➖ N/A (with activation condition)
# 2. Fill EVIDENCE with the command run or file read that supports the finding.
# 3. Items marked ➖ N/A must document WHEN they would activate.
# 4. After completing, derive findings per audit-system §5 (Blocking /
#    Non-blocking / Observation) and open tasks in Asana accordingly.
#
# ITEM FORMAT
# -----------
# ### ASVS-REF — Short description
# **Level:** L1 / L2 / L3
# **Status:** [ ]
# **Evidence:** _fill during audit_
# **Notes:** _optional context or finding_
#
# Reference: https://owasp.org/www-project-application-security-verification-standard/
# Standard version: OWASP ASVS 5.0.0 (May 2025)
# Last updated: [DATE]
# Audited by: [NAME/CHAT]
# Scope: [DESCRIBE WHAT WAS INCLUDED AND EXCLUDED]

---

## V1 — Encoding and Sanitization

*Protects against injection attacks and XSS through proper output encoding
and input sanitization at trust boundaries.*

### v5.0.0-1.1 — Injection Prevention

#### v5.0.0-1.1.1 — Output encoding for HTML contexts
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-1.1.2 — Output encoding for JavaScript contexts
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-1.1.3 — SQL queries use parameterised statements or ORM
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-1.1.4 — OS command injection prevention
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-1.1.5 — XML/XPath injection prevention
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V2 — Validation and Business Logic

*Ensures all input is validated, business rules are enforced server-side,
and invalid input is handled safely.*

### v5.0.0-2.1 — Input Validation

#### v5.0.0-2.1.1 — Server-side validation of all untrusted input
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-2.1.2 — Validation failures return safe error responses
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-2.1.3 — Structured data is strongly typed and validated
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-2.2 — Business Logic

#### v5.0.0-2.2.1 — Business logic flows execute in correct order
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-2.2.2 — Rate limiting or anti-automation controls on sensitive flows
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V3 — Web Frontend Security

*Browser-side security: headers, CSP, SRI, frame controls.*

### v5.0.0-3.1 — Browser Security Controls

#### v5.0.0-3.1.1 — Content-Security-Policy header present and restrictive
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-3.1.2 — X-Content-Type-Options: nosniff set
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-3.1.3 — X-Frame-Options or frame-ancestors CSP directive set
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-3.1.4 — Referrer-Policy header present
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-3.1.5 — Subresource Integrity (SRI) on external scripts/styles
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V4 — API and Web Service

*Security controls specific to REST/GraphQL APIs and web services.*

### v5.0.0-4.1 — API Security

#### v5.0.0-4.1.1 — API endpoints verify authentication on every request
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-4.1.2 — HTTP methods restricted to those needed per endpoint
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-4.1.3 — Content-Type validated on requests with body
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-4.1.4 — GraphQL introspection disabled in production
**Level:** L2
**Status:** ➖ N/A
**Activation condition:** project adds GraphQL endpoint
**Notes:**

---

## V5 — File Handling

*Safe handling of uploaded and downloaded files.*

### v5.0.0-5.1 — File Upload

#### v5.0.0-5.1.1 — File type validated server-side (not just by extension)
**Level:** L1
**Status:** ➖ N/A
**Activation condition:** project adds file upload functionality
**Notes:**

#### v5.0.0-5.1.2 — Uploaded files stored outside web root or with execution disabled
**Level:** L1
**Status:** ➖ N/A
**Activation condition:** project adds file upload functionality
**Notes:**

#### v5.0.0-5.1.3 — File size limits enforced server-side
**Level:** L1
**Status:** ➖ N/A
**Activation condition:** project adds file upload functionality
**Notes:**

---

## V6 — Authentication

*Credential management, password policies, MFA, account recovery.*

### v5.0.0-6.1 — Authentication Design

#### v5.0.0-6.1.1 — Authentication state checked on every protected request
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-6.1.2 — Failed authentication does not reveal which credential is wrong
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-6.2 — Credential Storage

#### v5.0.0-6.2.1 — Passwords hashed with modern adaptive algorithm (bcrypt/Argon2/scrypt)
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-6.2.2 — No credentials stored in plaintext or reversible encoding
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-6.3 — Credential Recovery

#### v5.0.0-6.3.1 — Password reset tokens are single-use and expire within short TTL
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-6.3.2 — Recovery flow does not leak registered email/username
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V7 — Session Management

*Session token generation, storage, expiry, and revocation.*

### v5.0.0-7.1 — Session Tokens

#### v5.0.0-7.1.1 — Session tokens have sufficient entropy (≥128 bits)
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-7.1.2 — Session ID regenerated after successful authentication
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-7.1.3 — Sessions invalidated on logout server-side
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-7.2 — Cookie Security

#### v5.0.0-7.2.1 — Session cookies have HttpOnly flag
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-7.2.2 — Session cookies have Secure flag
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-7.2.3 — Session cookies have SameSite=Lax or Strict
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-7.3 — Session Expiry

#### v5.0.0-7.3.1 — Idle session timeout enforced server-side
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-7.3.2 — Absolute session lifetime enforced (not just idle)
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V8 — Authorization

*Access control: who can do what, enforced server-side.*

### v5.0.0-8.1 — Access Control Design

#### v5.0.0-8.1.1 — Access control enforced on trusted server layer, not client
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-8.1.2 — Default deny: access denied unless explicitly granted
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-8.1.3 — Users can only access their own resources (IDOR prevention)
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-8.1.4 — Directory listing disabled
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V9 — Self-Contained Tokens (JWT)

*JWT and similar token security.*

### v5.0.0-9.1 — Token Security

#### v5.0.0-9.1.1 — JWT signature verified on every request
**Level:** L1
**Status:** ➖ N/A
**Activation condition:** project uses JWT
**Notes:**

#### v5.0.0-9.1.2 — alg:none and weak algorithms rejected
**Level:** L1
**Status:** ➖ N/A
**Activation condition:** project uses JWT
**Notes:**

#### v5.0.0-9.1.3 — JWT expiry (exp claim) validated
**Level:** L1
**Status:** ➖ N/A
**Activation condition:** project uses JWT
**Notes:**

---

## V10 — OAuth and OIDC

*OAuth 2.0 and OpenID Connect flows.*

### v5.0.0-10.1 — OAuth Client Security

#### v5.0.0-10.1.1 — state parameter used and validated (CSRF prevention)
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-10.1.2 — Authorization codes single-use only
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-10.1.3 — Redirect URIs strictly validated against allowlist
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-10.1.4 — Access tokens not stored in browser-accessible storage
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-10.1.5 — Refresh token rotation enforced
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V11 — Cryptography

*Key management, algorithm selection, random number generation.*

### v5.0.0-11.1 — Cryptographic Algorithms

#### v5.0.0-11.1.1 — Only approved cryptographic algorithms in use
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-11.1.2 — No custom cryptographic implementations
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-11.1.3 — Cryptographically secure RNG used for security-sensitive values
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-11.2 — Key Management

#### v5.0.0-11.2.1 — Cryptographic keys not hardcoded in source code
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-11.2.2 — Encryption keys stored separately from encrypted data
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V12 — Secure Communication

*TLS configuration and certificate validation.*

### v5.0.0-12.1 — TLS

#### v5.0.0-12.1.1 — TLS used for all external connections carrying sensitive data
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-12.1.2 — TLS version ≥ 1.2; TLS 1.0 and 1.1 disabled
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-12.1.3 — Certificate validation not disabled in backend HTTP clients
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V13 — Configuration

*Security hardening of the runtime environment and dependencies.*

### v5.0.0-13.1 — Build and Deployment

#### v5.0.0-13.1.1 — No debug features enabled in production build
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-13.1.2 — Dependencies come from trusted, integrity-verified sources
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-13.2 — Secrets Management

#### v5.0.0-13.2.1 — No secrets committed to version control
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-13.2.2 — Secrets loaded from environment variables or secrets manager
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-13.2.3 — .env files excluded from version control via .gitignore
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V14 — Data Protection

*Classification, encryption at rest, and minimisation of sensitive data.*

### v5.0.0-14.1 — Data Classification

#### v5.0.0-14.1.1 — Sensitive data identified and documented
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-14.1.2 — Sensitive data encrypted at rest
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-14.1.3 — Sensitive data not logged
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-14.1.4 — Caches and temporary storage cleared of sensitive data when no longer needed
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V15 — Secure Coding and Architecture

*Security decisions documented; dependency hygiene; general architecture.*

### v5.0.0-15.1 — Security Architecture

#### v5.0.0-15.1.1 — Security decisions documented and reviewable
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-15.1.2 — Principle of least privilege applied to service accounts and components
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-15.2 — Dependency Security

#### v5.0.0-15.2.1 — Known vulnerable dependencies identified and tracked
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-15.2.2 — Process exists to update vulnerable dependencies promptly
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V16 — Security Logging and Error Handling

*Audit trails and safe error responses.*

### v5.0.0-16.1 — Logging

#### v5.0.0-16.1.1 — Authentication events logged (success and failure)
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-16.1.2 — Access control failures logged
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-16.1.3 — Logs do not contain sensitive data (passwords, tokens, PII)
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-16.1.4 — Log integrity protected (append-only or write-once where possible)
**Level:** L2
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### v5.0.0-16.2 — Error Handling

#### v5.0.0-16.2.1 — Error responses do not expose stack traces or internal paths in production
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

#### v5.0.0-16.2.2 — Generic error messages shown to users; detail in server logs only
**Level:** L1
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## V17 — WebRTC

*Real-time communication security.*

### v5.0.0-17.1 — WebRTC Security

#### v5.0.0-17.1.1 — ICE candidate filtering to prevent IP leakage
**Level:** L2
**Status:** ➖ N/A
**Activation condition:** project adds WebRTC functionality
**Notes:**

---

## Audit summary

**Date:** [DATE]
**Auditor:** [NAME/CHAT]
**Scope:** [WHAT WAS INCLUDED/EXCLUDED]
**ASVS version:** 5.0.0 Level 2

| Result | Count |
|---|---|
| ✅ PASS | |
| ❌ FAIL | |
| ⚠️ PARTIAL | |
| ➖ N/A | |
| **Total active items** | |

**Blocking findings:** [list or "none"]
**Non-blocking findings:** [list or "none"]
**Observations:** [list or "none"]
