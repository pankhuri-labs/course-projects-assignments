# Secure Web Hosting with Apache, FTP and SELinux

**Course:** Professional Certificate Programme in Cybersecurity and AI, IIT Madras · **Type:** Graded mini project 1 (week 2) · **Year:** 2025

> **Summary:** Built a Linux web host from scratch and secured it with SELinux in enforcing mode, so Apache could serve only the content it was explicitly labelled to serve. Shows hands-on understanding of secure service deployment and mandatory access control, the kind of baseline hardening that platform security standards ask engineering teams to meet.

## Objective
Deploy and secure a web hosting environment on CentOS Stream 9: Apache with a custom virtual host, FTP and SSH services, local DNS resolution, and SELinux enforcing safe access to files exposed through a symbolic link.

## Approach
- Installed CentOS Stream 9 on VMware Workstation and set up root access.
- Installed and verified `openssh-server`, `vsftpd` and `httpd`, troubleshooting SSH set-up errors and opening the firewall for FTP.
- Created an Apache virtual host for `testsite.mydomain.local` with its own document root and mapped it in `/etc/hosts`.
- Linked a `/reports` directory into the site, turned on SELinux enforcement (`setenforce 1`), checked contexts with `ls -lZ` and applied the correct labels with `chcon`.

## Outcome
The virtual host and the `/reports` path both loaded in the browser with SELinux in enforcing mode, with symbolic linking and file permissions verified.

## Tools
CentOS Stream 9, VMware Workstation, Apache HTTPD, vsftpd, OpenSSH, SELinux (`setenforce`, `chcon`, `ls -lZ`)

## Files
- [`secure_web_hosting_selinux_report.pdf`](secure_web_hosting_selinux_report.pdf): step-by-step report with screenshots
