# Capstone: Secure File Storage with Access Control and Auditing

**Course:** Professional Certificate Programme in Cybersecurity and AI, IIT Madras · **Type:** Capstone project (week 30) · **Year:** 2026

> **Summary:** Designed, built and tested a layered set of controls for a shared file store used by two project teams: role-based access, ACLs, deletion protection, command-history accountability, kernel-level audit logging and a password-protected web report of the audit trail that refreshes automatically. The controls were tested by attempting the actions they should block. This is the control-design, evidence and audit thinking that governance and compliance programmes depend on.

## Objective
Implement and validate a secure file storage and access management system in Linux that keeps teams isolated, prevents unauthorised changes and leaves a complete, reviewable audit trail.

## Approach
1. **Identity and groups:** created four users in two team groups (`teamA`, `teamB`) and a shared `/capstone_project` directory.
2. **Permissions and ACLs:** `chmod 2770` (setgid so new files inherit the group; no access for others) and default ACLs with `setfacl` / `getfacl` for team-level access.
3. **Deletion protection:** sticky bit (`chmod +t`) so only a file's owner can delete it.
4. **Accountability:** bash as the default shell and command-history settings checked for each user.
5. **Auditing:** installed `auditd`, wrote rules to watch the shared directory and verified events with `ausearch`, including the failed deletion attempt.
6. **Audit reporting:** published the audit trail to an Apache page protected with `.htaccess` basic authentication, refreshed by a cron-scheduled script.
7. **Validation:** tested the controls, for example another user trying to edit or delete a file they don't own.

## Outcome
Another user was denied when trying to modify or delete a file they didn't own ("Operation not permitted"), the denied deletion appeared in both `ausearch` and the web audit report, and the report was served behind basic authentication.

## Tools
Kali Linux, VMware Workstation, `useradd` / `usermod` / `groupadd`, `chmod` / `chown`, `setfacl` / `getfacl`, `auditd` / `auditctl` / `ausearch`, Apache2, `htpasswd` / `.htaccess`, cron

## Files
- [`linux_access_control_auditing_capstone_report.pdf`](linux_access_control_auditing_capstone_report.pdf): full report with commands and screenshots
