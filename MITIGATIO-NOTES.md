# Task 3 — Mitigation Notes

## 1. SQL Injection
- Use prepared statements and parameterized queries.
- Avoid building SQL queries by concatenating user input.
- Apply least-privilege database permissions.
- Validate inputs and handle database errors safely.

**Lab note:** A separate PHP prepared-statement demonstration was tested.

## 2. Cross-Site Scripting (XSS)
- Encode output according to its HTML, attribute, or JavaScript context.
- Sanitize permitted HTML with a suitable library.
- Avoid inserting untrusted input through unsafe DOM APIs.
- Use Content Security Policy as an additional defense, not as a replacement for output encoding.

## 3. Cross-Site Request Forgery (CSRF)
- Validate unpredictable CSRF tokens on state-changing requests.
- Use SameSite cookie settings and secure session handling.
- Verify request origin where appropriate.
- Require appropriate re-authentication for sensitive actions.

**Lab note:** The token-protection demonstration was a separate PHP example, not an integration into DVWA.

## 4. Local File Inclusion (LFI)
- Use an allowlist of permitted page names.
- Never pass arbitrary user input directly to file-inclusion functions.
- Resolve paths safely and prevent directory traversal.
- Keep sensitive files outside web-accessible directories.

## 5. Remote File Inclusion (RFI)
- Disable `allow_url_include` in production PHP configurations.
- Never include remote resources based on untrusted input.
- Use an allowlist of trusted resources and restrict outbound access.

**Lab note:** RFI testing required a deliberately unsafe local PHP configuration. Restore the secure setting after testing.

## 6. HTTP Security Headers
- Configure Content-Security-Policy (CSP).
- Set X-Content-Type-Options to `nosniff`.
- Set X-Frame-Options or use CSP `frame-ancestors`.
- Set an appropriate Referrer-Policy.
- Restrict browser features with Permissions-Policy where suitable.

**Lab note:** Apache headers were configured and checked locally. The SecurityHeaders.com screenshot for example.com is not evidence of the local DVWA site's grade.

## 7. General Recommendations
- Keep the operating system, web server, PHP, and database updated.
- Use HTTPS for deployed applications.
- Apply least privilege and secure session management.
- Retest after changes and retain screenshots as evidence.

## Verification
Only claim that a vulnerability is fixed when the mitigation has been applied and its behavior has been retested successfully. A configuration change alone does not prove complete remediation.
