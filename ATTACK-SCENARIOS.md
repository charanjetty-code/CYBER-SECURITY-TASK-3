
# Task 3 — Attack Scenarios

All tests were performed in a controlled local lab using DVWA and intentionally vulnerable applications.

## 1. SQL Injection (SQLi)
**Scenario:** Entered a crafted input into the DVWA SQL Injection field:
`1' OR '1'='1' #`

**Observation:** The application returned multiple database records instead of a single expected result, demonstrating how unsafe SQL query construction can expose data.

**Impact:** Unauthorized data access and possible database manipulation.

## 2. Cross-Site Scripting (XSS)
**Scenario:** Tested script input in the DVWA reflected and stored XSS exercises.

**Observation:** The application processed the test input in a way that demonstrated the risk of executing untrusted content in a browser.

**Impact:** Depending on context, XSS can enable page manipulation or actions in a victim's browser.

## 3. Cross-Site Request Forgery (CSRF)
**Scenario:** Tested the DVWA password-change flow and a separate token-protection demonstration.

**Observation:** The DVWA exercise illustrated the risk of accepting a sensitive request without sufficient protection. The separate demo checked whether a submitted token was validated.

**Impact:** An authenticated user could be tricked into submitting an unwanted action if CSRF defenses are inadequate.

## 4. Local File Inclusion (LFI)
**Scenario:** Tested a file parameter using `/etc/passwd` in the controlled lab.

**Observation:** Local file contents were exposed, demonstrating unsafe file-path handling.

**Impact:** Disclosure of sensitive system files.

## 5. Remote File Inclusion (RFI)
**Scenario:** Tested a deliberately configured local PHP lab with a test file served locally.

**Observation:** The test demonstrated the risk of allowing user-controlled input to include remote resources.

**Impact:** Under unsafe configurations, this can lead to unauthorized code execution.

## 6. Burp Suite Request Testing
**Scenario:** Intercepted and modified a login request and sent test payloads to the SQL injection endpoint.

**Observation:** The modified login attempt failed. The payload requests returned HTTP 200 responses with varying response lengths; those results alone do not prove a successful exploit.

## Scope
These exercises were conducted for educational purposes in a local lab. No third-party systems were targeted.
