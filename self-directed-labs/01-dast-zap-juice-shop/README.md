# DAST on OWASP Juice Shop with OWASP ZAP

**Type:** Self-directed lab · **Year:** 2026

> **Summary:** Ran OWASP ZAP against OWASP Juice Shop in two configurations and compared what each could see. A traditional crawl found 5 alert types; adding a browser-based (AJAX) crawl raised that to 9, all of them header and configuration issues, and neither run reached the injection flaws Juice Shop is known for. The lab confirmed, from the inside, three things I would build into any DAST programme: measure crawl coverage, require authenticated scans, and group findings by fix rather than by URL.

## Objective
Understand what an unauthenticated DAST scan actually covers on a modern single-page app, how much of its output is real, and what that means for how a scanning programme sets coverage targets, triage rules and "scan clean" gates.

## Approach
- Ran Juice Shop (an intentionally vulnerable Angular app) in Docker on my own machine.
- **Run 1:** ZAP automated scan with the traditional spider and active scan.
- **Run 2:** same target with the AJAX spider driving a real browser, then the active scan.
- Triaged every alert type in both runs: risk, CWE, where it occurs, whether it is real or noise, and the one-line fix.
- Exported the results as HTML (to read) and XML (for import into a vulnerability management platform in the next lab).

## Outcome

| | Run 1: traditional spider | Run 2: + AJAX spider |
|---|---|---|
| Alert types | 5 | 9 |
| By risk | 2 Medium, 3 Informational | 4 Medium, 3 Low, 2 Informational |
| High-risk findings | 0 | 0 |
| Injection flaws (SQLi, XSS) | Not reached | Not reached |

**Triage of Run 2**

| Alert | Risk | CWE | Scope | Verdict | Fix |
|---|---|---|---|---|---|
| Content Security Policy header not set | Medium | 693 | Every page | Real | Add a `Content-Security-Policy` header |
| Cross-domain misconfiguration (`Access-Control-Allow-Origin: *`) | Medium | 264 | Every response | Real; risky on APIs that return user data | Allow only trusted origins |
| Missing anti-clickjacking header | Medium | 1021 | 3 pages | Real | `frame-ancestors 'self'` in CSP |
| Session ID in URL rewrite | Medium | 598 | Systemic | Needs triage: likely a WebSocket transport ID, not a login session | Keep session tokens out of URLs |
| Private IP disclosure | Low | 497 | 1 response | Real, low impact | Strip internal IPs from responses |
| Timestamp disclosure | Low | 497 | 4 | Mostly noise (build timestamps) | None unless sensitive |
| `X-Content-Type-Options` missing | Low | 693 | 5 | Real | `X-Content-Type-Options: nosniff` |
| Suspicious comments | Info | 615 | 4 JS files | Mostly noise in minified code | Strip comments in production builds |
| Modern web application | Info | — | Site-wide | Not a vulnerability: ZAP flagging that a browser crawl is needed | — |

Also observed: error responses exposing framework stack traces and internal file paths (CWE-209), which ZAP did not raise as a separate alert. Fix: generic error pages in production.

## What I would change in a scanning programme
1. **Report crawl coverage next to findings.** Run 1 looked like a modest, clean result; it was really a shallow crawl. A DAST dashboard that shows finding counts without pages, endpoints or API routes reached invites false confidence. Coverage should be a tracked metric, and a low-coverage scan should not count as a pass.
2. **Make authenticated scanning the default for anything with a login.** Neither run touched the logged-in API calls (login, search, basket) where the serious flaws live. An unauthenticated scan is a configuration check, not an application test, and release gates should say so.
3. **Group findings by remediation path, not by URL.** Most of the 9 alert types (CSP, clickjacking, nosniff) are fixed by one security-headers change at the framework or gateway level. Raising a ticket per page per alert would bury teams in duplicates; a programme should route systemic findings to the platform owner as a single fix.
4. **Budget for triage, and write the rules down.** Roughly a third of the alert types were noise or needed judgement (timestamps, comments, a transport ID that looked like a session ID). Clear "real vs noise" rules per alert type, and suppressions that are reviewed rather than permanent, keep developer trust in the tool.
5. **Treat setup friction as an adoption cost.** Getting the browser crawl working needed a driver version matched to the installed browser. If that slows down one experienced person, it will stall a product team. A paved road (a pre-configured scanner image, pinned versions, a one-page guide) does more for coverage than a policy mandate.

## Tools
OWASP ZAP (traditional spider, AJAX spider, active scan), OWASP Juice Shop, Docker

## Next
- Import these results into DefectDojo to practise deduplication, triage, SLAs and programme metrics.
- Authenticated ZAP scan to reach the API layer, with findings mapped to the OWASP Top 10 and ASVS.
