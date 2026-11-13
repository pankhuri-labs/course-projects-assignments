# Professional Certificate Programme in Cybersecurity and AI, IIT Madras (2025–26)

Graded projects from IIT Madras's Professional Certificate Programme in Cybersecurity and AI, completed alongside my role leading application security and DevSecOps programmes at enterprise scale. I did the work hands-on in my own virtual lab (VMware with Kali Linux, CentOS, Windows Server 2022 and intentionally vulnerable targets).

**Why it's here:** I lead security programmes rather than run scanners day to day. These projects show that the decisions I make about controls, detection, tooling and AI in security operations are grounded in having built and broken those controls myself.

## At a glance

| # | Project | Area | What it shows | Tools | Outcome (from the report) |
|---|---|---|---|---|---|
| 01 | [Secure web hosting with SELinux](01-secure-web-hosting-selinux/) | Infrastructure hardening | Secure service deployment, least privilege through mandatory access control | CentOS Stream 9, Apache, vsftpd, OpenSSH, SELinux | Virtual host served and validated with SELinux in enforcing mode |
| 02 | [Credential exposure in network traffic](02-network-traffic-credential-exposure/) | Network security | Why plaintext protocols are a risk and how TLS and SNI protect data in transit | Wireshark, Kali Linux, bWAPP / bee-box | HTTP and FTP credentials captured in plaintext; HTTPS traffic analysed through the TLS Client Hello |
| 03 | [AI-assisted DNS spoofing (MITM)](03-dns-spoofing-mitm-ai-assisted/) | Offensive security, GenAI | How ARP poisoning and DNS spoofing redirect users; where GenAI speeds up and where it needs verifying | Kali Linux, Ettercap, Apache2, ChatGPT, Windows Server 2022 | Victim's DNS lookup resolved to the attacker host and served the spoofed page |
| 04 | [AI in the SOC: Colonial Pipeline case analysis](04-ai-soc-incident-analysis-colonial-pipeline/) | Incident analysis, AI governance | Mapping a real incident to CIA, AAA and NIST CSF; limits, adversarial risks and accountability of AI in the SOC | NIST CSF, MITRE ATT&CK, UEBA / SOAR concepts | Seven-stage timeline and seven improvement recommendations (MFA, Zero Trust, UEBA, SOAR, adversarial testing) |
| 05 | [Security log analysis in Splunk](05-security-log-analysis-splunk/) | Detection and monitoring | AI-assisted automation of log collection and analysis for blue-team monitoring | PowerShell, Splunk Enterprise (SPL), ChatGPT | 430 Windows Security events exported, indexed and analysed with five SPL queries |
| 06 | [Digital forensics: steganography and deleted-file recovery](06-digital-forensics-steganography/) | Forensics and incident response | Evidence preservation and recovery of concealed and deleted data | SilentEye, FTK Imager, Autopsy | Deleted stego-image recovered from an E01 image and the hidden message decoded |
| 07 | [Capstone: secure file storage with access control and auditing](07-capstone-linux-access-control-auditing/) | Access control, audit and compliance | Designing and validating layered controls: RBAC, ACLs, sticky bit, auditd, protected web reporting | Linux (Kali), setfacl, auditd / ausearch, Apache, .htaccess, cron | Unauthorised edits and deletions blocked, the denied deletion captured in the audit trail, password-protected audit report refreshed by cron |

## Skills shown
- **Security controls:** role-based access control, Linux permissions and ACLs, SELinux, least privilege, audit logging
- **Detection and response:** Windows Security event analysis, SPL, log pipelines, digital forensics and evidence handling
- **Attack techniques (lab only):** traffic sniffing, ARP poisoning, DNS spoofing, steganography
- **Frameworks:** CIA triad, AAA, NIST Cybersecurity Framework, MITRE ATT&CK, Zero Trust
- **AI in security:** using GenAI to generate scripts and queries and to troubleshoot, and judging its output; AI limitations, adversarial risks and governance in the SOC

## Repository layout
Each project folder holds a `README.md` (summary: objective, approach, outcome, tools) and the submitted report as a PDF.

```
iitm-cybersecurity-ai-2026/
  01-secure-web-hosting-selinux/
  02-network-traffic-credential-exposure/
  03-dns-spoofing-mitm-ai-assisted/
  04-ai-soc-incident-analysis-colonial-pipeline/
  05-security-log-analysis-splunk/
  06-digital-forensics-steganography/
  07-capstone-linux-access-control-auditing/
```

All attack work was done in an isolated lab against machines I controlled or against intentionally vulnerable test targets. Course-provided task briefs and lab guides are not included, as they belong to the programme.
