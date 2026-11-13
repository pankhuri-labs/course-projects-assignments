# AI in the SOC: Colonial Pipeline Ransomware Case Analysis

**Course:** Professional Certificate Programme in Cybersecurity and AI, IIT Madras · **Type:** Graded mini project (case analysis) · **Year:** 2026

> **Summary:** Analysed the 2021 Colonial Pipeline ransomware attack through the lens of an AI-driven SOC: what AI-based detection and response could and could not have caught, how attackers evade it, and who is accountable when it misses. The most leadership-oriented project in the set: it ties a real incident to frameworks, governance and a prioritised improvement plan.

## Objective
Assess how AI-driven security operations apply to a major critical-infrastructure incident, and where they fall short.

## Approach
- **Incident timeline:** seven stages from initial access through compromised VPN credentials with no MFA, through lateral movement, DarkSide ransomware deployment, detection, the containment shutdown and public impact, to recovery.
- **Impact analysis:** CIA triad (availability hit hardest) and the AAA model (authentication failed without MFA; excessive privileges; weak monitoring of login anomalies).
- **NIST CSF mapping:** where AI supports Identify, Protect, Detect, Respond and Recover, and where it was or wasn't used in this case.
- **AI techniques and limits:** ML anomaly detection, UEBA, SOAR, NLP; why credential-based, low-and-slow attacks look "normal" to models.
- **Adversarial techniques against AI:** living off the land with valid credentials, blending in with normal behaviour, data poisoning.
- **Governance:** decision authority for AI, ethics of paying ransoms and of automated shutdowns, explainability, and accountability for missed detections.

## Outcome
Concludes that AI-driven SOC capability is not enough without strong identity security, governance and human oversight, and recommends seven improvements: MFA everywhere, Zero Trust, more mature UEBA, better SOAR playbooks, continuous model training and validation, adversarial testing of AI systems, and stronger real-time logging and monitoring.

## Frameworks and references
CIA triad, AAA, NIST Cybersecurity Framework, MITRE ATT&CK, UEBA and SOAR concepts; sources include CISA, FBI IC3, NIST and ENISA.

## Files
- [`colonial_pipeline_ai_soc_analysis.pdf`](colonial_pipeline_ai_soc_analysis.pdf): full analysis
