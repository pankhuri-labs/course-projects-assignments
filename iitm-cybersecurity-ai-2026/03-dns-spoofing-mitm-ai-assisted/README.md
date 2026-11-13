# AI-Assisted DNS Spoofing (Man-in-the-Middle) with Ettercap

**Course:** Professional Certificate Programme in Cybersecurity and AI, IIT Madras · **Type:** Graded mini project 3 (week 13) · **Year:** 2026

> **Summary:** Ran a man-in-the-middle attack in an isolated lab, poisoning ARP and spoofing DNS so a Windows Server victim was silently sent to an attacker-controlled web page, using ChatGPT as a guide and troubleshooter throughout. Shows how name-resolution attacks work, and a practical view of where GenAI speeds up security work and where its output still needs human verification.

## Objective
Simulate DNS spoofing in a virtual lab with Kali Linux as the attacker and Windows Server 2022 as the victim, using generative AI for step-by-step guidance.

## Approach
- Configured the attacker network, enabled IP forwarding (temporarily and permanently in `/etc/sysctl.conf`) and confirmed connectivity to the victim and gateway.
- Installed Ettercap (GUI) and Apache2 and hosted the page to be served to the victim.
- Recorded a baseline: the target domain resolved to its real public IP on the victim before the attack.
- Mapped the target domain to the attacker's IP in `etter.dns` and reviewed `etter.conf`.
- Discovered hosts, set the victim and default gateway as targets, started ARP poisoning and activated the `dns_spoof` plugin.
- Used ChatGPT to troubleshoot; the fix for the initial failed redirection was the plugin activation order and a service restart.

## Outcome
After flushing its DNS cache, the victim resolved the target domain to the Kali host and the browser showed the attacker's Apache page with no visible warning. The report concludes that AI was an effective assistant but not a substitute for manual verification and technical reasoning.

## Tools
Kali Linux, Ettercap 0.8.3.1, Apache2, Windows Server 2022, VMware Workstation, ChatGPT

## Files
- [`dns_spoofing_mitm_report.pdf`](dns_spoofing_mitm_report.pdf): step-by-step report with screenshots

Performed only in an isolated virtual network against a machine I controlled.
