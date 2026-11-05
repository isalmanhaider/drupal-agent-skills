# Security pass

Apply this to every change that handles input, output, access, files, URLs
or credentials.

## What to look for

- SQL injection
- Cross-site scripting (XSS) and incorrect output escaping
- Cross-site request forgery (CSRF), including state-changing GET routes
  without a `_csrf_token` requirement
- Broken access control, insecure direct object references (IDOR),
  authentication bypass and privilege escalation
- Sensitive information disclosure, including personal data written to
  logs
- Unsafe file uploads, and sensitive files stored under `public://`
  instead of `private://`
- Path traversal
- Server-side request forgery (SSRF)
- Unsafe deserialization
- Command injection
- Insecure redirects
- Hardcoded secrets, and environment-specific hosts or credentials in code
- Insecure API integrations: missing timeouts, disabled TLS verification,
  unvalidated responses
- Missing input validation

## For each potential vulnerability

1. Identify the entry point.
2. Trace the relevant data flow.
3. Identify existing protections, such as Form API tokens, route access
   requirements, Twig autoescaping and entity access handlers.
4. Decide whether exploitation is plausible.
5. Describe the impact and the preconditions.

Admin-only surfaces are not vulnerabilities by themselves: say which
permission an attacker would need. Never claim exploitability without
supporting evidence.
