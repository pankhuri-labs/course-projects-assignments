# Credential Exposure in Network Traffic with Wireshark

**Course:** Professional Certificate Programme in Cybersecurity and AI, IIT Madras · **Type:** Graded mini project 2 (week 4) · **Year:** 2025

> **Summary:** Captured usernames and passwords travelling in plaintext over HTTP and FTP, then compared them with HTTPS, where only the TLS handshake is visible. A first-hand demonstration of why "encrypt everything in transit" is a non-negotiable control, and of how TLS and SNI work.

## Objective
Analyse network traffic from a deliberately vulnerable machine to see how insecure protocols expose credentials, and how HTTPS protects data in transit.

## Approach
- Deployed the bee-box VM (bWAPP, an intentionally vulnerable web app) in VMware and attacked from Kali Linux.
- Logged in to bWAPP over HTTP and used Wireshark `http` filters to read the username and password from the captured packets.
- Logged in over FTP and found the credentials in plaintext in the FTP packets.
- Browsed to an HTTPS site, filtered on TCP port 443 and read the server name (SNI) from the TLS Client Hello.
- Tried the extracted IP address directly over HTTPS to test redirection behaviour.

## Outcome
HTTP and FTP credentials were fully readable in the capture; HTTPS content was not. Going to the HTTPS site by raw IP address failed, because certificates are bound to domain names and the server relies on SNI to pick the right one.

## Tools
Wireshark, Kali Linux, bee-box / bWAPP, VMware Workstation

## Files
- [`wireshark_credential_analysis_report.pdf`](wireshark_credential_analysis_report.pdf): step-by-step report with screenshots

All credentials shown are the default test accounts of the bee-box training VM.
