# Self-directed security labs

Labs I set up and ran on my own, outside any course, to test the tools my programmes depend on. Each one runs against a deliberately vulnerable app on my own machine.

**Why it's here:** I lead application security and vulnerability management programmes. When I decide how a scanner is rolled out, what "clean" means or how findings flow to teams, I want that grounded in having run the tool and triaged its output myself. Each write-up ends with what I would change in a programme because of what I found.

| # | Lab | Area | Tools | Programme takeaway |
|---|---|---|---|---|
| 01 | [DAST on OWASP Juice Shop](01-dast-zap-juice-shop/) | Dynamic application security testing | OWASP ZAP, Docker, OWASP Juice Shop | Crawl coverage decides what a DAST scan can find; a clean unauthenticated scan is not evidence of a secure app |

All scanning was done against local, intentionally vulnerable targets I control. Active scanning is an attack, so it is never pointed at anything else.
