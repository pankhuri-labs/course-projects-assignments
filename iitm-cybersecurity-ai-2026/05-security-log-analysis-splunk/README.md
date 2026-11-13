# Windows Security Log Analysis in Splunk with AI-Generated Automation

**Course:** Professional Certificate Programme in Cybersecurity and AI, IIT Madras · **Type:** Graded mini project (week 27) · **Year:** 2026

> **Summary:** Built a small blue-team monitoring pipeline: a ChatGPT-generated PowerShell script exported a week of Windows Security events, which were indexed in Splunk and analysed with AI-drafted SPL queries for logins, account creation and privilege changes. Shows how GenAI can speed up SOC automation, and the validation it still needs.

## Objective
Simulate a security monitoring workflow by automating the collection and analysis of Windows Security Event Logs.

## Approach
- Prompted ChatGPT for a PowerShell script to export the last seven days of Security events to CSV, then ran it as Administrator.
- Installed Splunk Enterprise, created a `security_logs` index and ingested the CSV.
- Prompted ChatGPT for SPL queries and ran five analyses: failed logons (event 4625), successful logons (4624), user creation (4720), privilege assignment and top event types.
- Sanity-checked the Splunk results against the source data.

## Outcome
430 events were exported, ingested and analysed. Activity was low, as expected for a lab VM. The cross-check found minor discrepancies between tools, which the report records rather than hides.

## Tools
PowerShell, Splunk Enterprise (SPL), Windows Server 2022, ChatGPT

## Files
- [`windows_security_log_analysis_splunk_report.pdf`](windows_security_log_analysis_splunk_report.pdf): report with prompts, script output, queries and screenshots
