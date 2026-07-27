# Phishing Infrastructure and OSINT Investigation

## Project Overview

This project demonstrates a safe investigation of a **simulated credential-phishing email** using passive OSINT and email-analysis techniques.

The investigation covers:

- Email-header analysis
- SPF, DKIM and DMARC review
- URL extraction and de-fanging
- Typosquatting and brand-impersonation analysis
- DNS and WHOIS checks
- VirusTotal, urlscan.io and Certificate Transparency research
- IOC documentation
- Infrastructure relationship mapping
- Attack-timeline reconstruction
- MITRE ATT&CK mapping
- Detection and containment recommendations

All suspicious infrastructure in the initial case is simulated. No live phishing site was opened, no credentials were submitted and no malicious files were downloaded.

## Simulated Scenario

A user received an email claiming to be from the PayPal Security Team. The message warned that the account had been restricted and directed the user to this defanged URL:

```text
hxxps://paypa1-security[.]example/login
```

The domain replaces the letter `l` with the number `1`, demonstrating a common typosquatting technique.

## Key Findings

- Brand impersonation
- Typosquatted sender domain
- Urgent account-restriction language
- Credential-themed `/login` path
- SPF failure
- Missing DKIM signature
- DMARC failure
- Matching sender and phishing URL domains
- No legitimate relationship with the impersonated organisation

## Final Assessment

| Category | Assessment |
|---|---|
| Threat type | Credential phishing |
| Delivery method | Email |
| Likelihood | High |
| Potential impact | High |
| Overall risk | High |
| Analyst confidence | High |

## Tools Used

- Kali Linux
- Linux command line
- `grep`
- `dig`
- `host`
- `whois`
- VirusTotal
- urlscan.io
- crt.sh
- MITRE ATT&CK
- Markdown

## Investigation Workflow

```text
Suspicious Email
      |
      v
Header Analysis
      |
      v
URL Extraction
      |
      v
DNS and WHOIS Review
      |
      v
Passive Threat-Intelligence Checks
      |
      v
Infrastructure Mapping
      |
      v
IOC Documentation
      |
      v
Attack Timeline
      |
      v
MITRE ATT&CK Mapping
      |
      v
Final Report


## Important Files

- Final report: `reports/Phishing-Investigation-Report.md`
- Header analysis: `analysis/header-analysis.md`
- URL analysis: `analysis/url-analysis.md`
- Domain analysis: `analysis/domain-analysis.md`
- Infrastructure analysis: `analysis/infrastructure-analysis.md`
- Attack timeline: `analysis/attack-timeline.md`
- MITRE mapping: `analysis/mitre-attack-mapping.md`
- IOC list: `iocs/indicators.csv`

## MITRE ATT&CK Mapping

| Tactic | Technique | ID | Evidence status |
|---|---|---|---|
| Initial Access | Phishing: Spearphishing Link | T1566.002 | Observed |
| Execution | User Execution: Malicious Link | T1204.001 | Intended, not observed |
| Credential Access | Input Capture: Web Portal Capture | T1056.003 | Intended, not observed |

## Safety and Legal Scope

This repository is intended only for ethical cybersecurity education, defensive research and portfolio demonstration.

- All suspicious URLs remain defanged.
- The `.example` domain is used for documentation and testing.
- `192.0.2.44` is used as a documentation-only address.
- No active scanning or exploitation was performed.
- No private, stolen or restricted information was accessed.

## Author

**Nitin Sukthe**

Cybersecurity learner focused on SOC operations, phishing analysis, OSINT, threat intelligence and incident investigation.
