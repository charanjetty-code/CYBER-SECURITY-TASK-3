# CYBER-SECURITY-TASK-3# Task 3 — Web Application Security

**Internship:** Cybersecurity & Ethical Hacking  
**Organization:** ApexPlanet Software Pvt. Ltd.

## Overview

This task involved practical web application security testing in a controlled lab using Kali Linux, Apache, MariaDB, DVWA, and Burp Suite.

## Practical Exercises

### 1. SQL Injection (SQLi)
- Tested SQL injection behavior in the deliberately vulnerable DVWA application.
- Observed how crafted input could return multiple database records.
- Demonstrated parameterized queries using prepared statements.
- **Mitigation:** Prepared statements, input validation, and least-privilege database access.

### 2. Cross-Site Scripting (XSS)
- Practiced stored and reflected XSS in DVWA.
- Reviewed how unsafe output handling can allow browser-side script execution.
- **Mitigation:** Context-aware output encoding, safe DOM handling, and Content Security Policy (CSP).

### 3. Cross-Site Request Forgery (CSRF)
- Examined the DVWA password-change workflow.
- Created a separate demonstration of CSRF token validation.
- **Mitigation:** Server-side validation of session-bound CSRF tokens and appropriate SameSite cookie settings.

### 4. Local and Remote File Inclusion
- Tested local file inclusion in the training application.
- Demonstrated remote inclusion using a controlled local test file.
- **Mitigation:** Allowlisted file selection, restricted filesystem access, and disabling remote URL inclusion.

### 5. Burp Suite
- Intercepted and modified a DVWA login request.
- Used Intruder with a small test payload list.
- **Observation:** The modified login was rejected. Response differences alone do not prove a vulnerability.
- **Mitigation:** Server-side validation and careful request/response analysis.

### 6. HTTP Security Headers
- Enabled Apache security-header configuration.
- Verified local response headers.
- Reviewed an external SecurityHeaders.com scan of `example.com`.
- **Mitigation:** Configure and verify suitable CSP, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, and Permissions-Policy headers.

## Repository Structure

- `Task-3-Web-Application-Security-Report.docx` — detailed report
- `screenshots/` — genuine practical evidence
- `demo/` — demonstration video, when ready

## Key Learning Outcomes

- Recognizing common web application vulnerabilities.
- Understanding defensive coding techniques.
- Inspecting and modifying HTTP requests with Burp Suite.
- Configuring and verifying Apache security headers.
- Documenting security findings and remediation recommendations.

## Scope and Safety

All exploitation exercises were performed in a deliberately vulnerable local training environment. The external security-header scan was performed against `example.com`, not the local DVWA application. The CSRF token example was a separate demonstration, not an integrated DVWA fix.

**Evidence note:** Screenshots and video should be added only when available. This README documents the practicals and their mitigations; it does not claim that every vulnerability was fully remediated in DVWA.
