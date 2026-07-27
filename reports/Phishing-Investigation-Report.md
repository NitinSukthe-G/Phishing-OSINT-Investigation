# Phishing Infrastructure and OSINT Investigation Report

## Document Information

| Field | Details |
|---|---|
| Project | Phishing Infrastructure and OSINT Investigation |
| Case type | Simulated credential-phishing investigation |
| Analyst | Nitin Sukthe |
| Investigation date | 27 July 2026 |
| Classification | Training and portfolio project |
| Overall risk | High |
| Confidence | High |
| Status | Completed |

## 1. Executive Summary

A simulated phishing email impersonating the PayPal Security Team was investigated using email-header analysis, URL analysis, DNS and WHOIS checks, passive threat-intelligence research, Certificate Transparency review, infrastructure mapping and MITRE ATT&CK.

The message claimed that the recipient's account had been restricted and directed the user to a credential-themed URL hosted on a typosquatted domain.

The investigation identified:

- Brand impersonation
- Typosquatting
- Urgent account-restriction language
- Credential-themed `/login` path
- SPF failure
- Missing DKIM signature
- DMARC failure
- Matching sender and URL domains

The evidence supports classification as a **high-risk simulated credential-phishing attempt**.

No real phishing website was opened, no credentials were submitted, no malicious files were downloaded and no attacker-controlled infrastructure was contacted.

## 2. Objective

The objective was to document:

- Email-header findings
- Sender-authentication results
- Suspicious URLs
- Domain and DNS information
- WHOIS findings
- Public reputation and certificate information
- Infrastructure relationships
- Indicators of compromise
- Attack timeline
- MITRE ATT&CK mapping
- Risk assessment
- Detection opportunities
- Containment recommendations

## 3. Scope

### In Scope

- Simulated phishing email
- Simulated email header
- Defanged URL
- Sender email address
- Sender domain
- Mail hostname
- Documentation-only source IP
- Passive OSINT
- Legitimate baseline comparison
- MITRE ATT&CK mapping

### Out of Scope

- Opening a live phishing site
- Credential submission
- Malicious-file download
- Active scanning
- Exploitation
- Contacting attacker infrastructure
- Accessing private or stolen data

## 4. Tools

| Tool | Purpose |
|---|---|
| Kali Linux | Investigation environment |
| `grep` | URL and text extraction |
| `dig` | DNS review |
| `host` | Hostname resolution |
| `whois` | Domain and IP research |
| VirusTotal | Passive reputation research |
| urlscan.io | Historical public scan research |
| crt.sh | Certificate Transparency research |
| MITRE ATT&CK | Behaviour mapping |
| Markdown | Documentation |

## 5. Initial Evidence

### Sender Information

| Field | Value |
|---|---|
| Display name | PayPal Security Team |
| Sender | `security-alert@paypa1-security.example` |
| Return-Path | `security-alert@paypa1-security.example` |
| Mail hostname | `mail.paypa1-security.example` |
| Source IP | `192.0.2.44` |
| Subject | Urgent: Your account has been temporarily restricted |

### Defanged URL

```text
hxxps://paypa1-security[.]example/login
```

### Social-Engineering Techniques

- Urgency
- Fear of suspension
- Immediate verification request
- Brand impersonation
- Credential-themed link

## 6. Email-Header Analysis

| Control | Result | Meaning |
|---|---|---|
| SPF | Fail | Sending server was not authorised |
| DKIM | None | No cryptographic signature |
| DMARC | Fail | Authentication and alignment failed |

Authentication failures alone do not always prove phishing. In this case, they were combined with brand impersonation, typosquatting, urgency and a credential-themed URL.

## 7. URL Analysis

| Component | Value |
|---|---|
| Scheme | `hxxps` |
| Domain | `paypa1-security[.]example` |
| Path | `/login` |
| Parameters | None |
| Status | Simulated and defanged |

Suspicious characteristics included:

1. PayPal-like brand name
2. Number `1` replacing the letter `l`
3. Trust-themed word `security`
4. Credential-themed `/login` path
5. Urgent account-verification context

## 8. Domain, DNS and WHOIS Analysis

The simulated domain was:

```text
paypa1-security[.]example
```

No active DNS records or normal registration information were expected because `.example` is reserved for documentation and testing.

The simulated source IP was:

```text
192.0.2.44
```

This address was used only for safe documentation.

The legitimate baseline was:

```text
paypal[.]com
```

The legitimate domain showed established public DNS, registration and certificate information.

## 9. Passive Threat-Intelligence Analysis

Passive searches were performed using VirusTotal, urlscan.io and crt.sh.

No suspicious URL was opened and no new scan was submitted.

The simulated domain had no meaningful public history, which was expected. The legitimate baseline showed established public infrastructure and reputation.

The absence of a public reputation result does not prove that a domain is safe. New malicious domains may initially have little or no public history.

## 10. Infrastructure Relationships

```text
Simulated Phishing Email
          |
          v
security-alert@paypa1-security.example
          |
          v
paypa1-security.example
          |
          +-- mail.paypa1-security.example
          |
          +-- 192.0.2.44
          |
          +-- hxxps://paypa1-security[.]example/login
                         |
                         v
            Intended Credential Collection
```

Key relationships:

- Sender, mail host and URL used the same simulated domain.
- The URL path suggested a login portal.
- Email authentication failed.
- No legitimate relationship with PayPal was identified.

## 11. Indicators

| Indicator | Type | Status |
|---|---|---|
| `security-alert@paypa1-security.example` | Email address | Simulated suspicious indicator |
| `paypa1-security.example` | Domain | Simulated suspicious indicator |
| `mail.paypa1-security.example` | Hostname | Simulated suspicious indicator |
| `192.0.2.44` | IP address | Documentation-only |
| `hxxps://paypa1-security[.]example/login` | URL | Simulated suspicious indicator |
| `/login` | URL path | Credential-themed path |

## 12. Timeline

| Time | Event |
|---|---|
| 09:09:40 IST | Simulated phishing email created |
| 09:10:25 IST | Email received |
| 09:10:25 IST | SPF failed |
| 09:10:25 IST | DKIM absent |
| 09:10:25 IST | DMARC failed |
| 09:11:00 IST | Recipient received urgent restriction message |
| 09:11:00 IST | Recipient instructed to visit login URL |
| 09:15:00 IST | Email reported |
| 09:20:00 IST | Indicators extracted |
| 09:30:00 IST | DNS and WHOIS checks completed |
| 09:45:00 IST | Passive OSINT completed |
| 10:00:00 IST | Infrastructure mapped |
| 10:15:00 IST | Email classified |

## 13. MITRE ATT&CK Mapping

| Tactic | Technique | ID | Status |
|---|---|---|---|
| Initial Access | Phishing: Spearphishing Link | T1566.002 | Observed |
| Execution | User Execution: Malicious Link | T1204.001 | Intended, not observed |
| Credential Access | Input Capture: Web Portal Capture | T1056.003 | Intended, not observed |

Only T1566.002 was directly supported by the simulated email. No user click or credential entry occurred.

## 14. Risk Assessment

| Factor | Rating |
|---|---|
| Threat type | Credential phishing |
| Delivery method | Email |
| Likelihood | High |
| Potential impact | High |
| Overall risk | High |
| Confidence | High |

### Justification

- Brand impersonation
- Typosquatting
- SPF failure
- Missing DKIM
- DMARC failure
- Urgent social engineering
- Credential-themed URL
- Matching sender and URL domains

## 15. Potential Impact

A successful attack could cause:

- Credential theft
- Account takeover
- Unauthorised transactions
- Personal-information exposure
- Password-reuse attacks
- Corporate account compromise
- Additional phishing
- Financial loss
- Reputational damage

## 16. Detection Opportunities

- Suspicious or newly observed sender domains
- SPF, DKIM and DMARC failures
- Typosquatted brand names
- Urgent account-verification messages
- Credential-themed URLs
- DNS requests for suspicious domains
- Proxy requests after email delivery
- Unusual sign-ins
- MFA changes
- New mailbox-forwarding rules

## 17. Containment Recommendations

1. Block the sender.
2. Block the domain and URL.
3. Search all mailboxes for similar messages.
4. Remove matching emails.
5. Identify users who clicked the link.
6. Reset credentials when interaction is confirmed.
7. Revoke active sessions and tokens.
8. Review MFA and identity-provider activity.
9. Review DNS and proxy logs.
10. Update SIEM and email-security rules.
11. Notify affected users.
12. Preserve all evidence.

## 18. Evidence Preservation

The following evidence was preserved:

- Simulated email
- Simulated email header
- Extracted URL
- Header analysis
- URL analysis
- DNS and WHOIS notes
- Passive OSINT notes
- Screenshots
- Infrastructure mapping
- IOC list
- Attack timeline
- MITRE mapping
- Final report

## 19. Limitations

- No real phishing site was opened.
- No credentials were entered.
- No suspicious file was downloaded.
- No malware was executed.
- No attacker system was contacted.
- No active scanning was performed.
- No real compromise occurred.

## 20. Conclusion

The simulated email was classified as a high-risk credential-phishing attempt.

The strongest indicators were brand impersonation, typosquatting, authentication failures, urgent account-verification language and a credential-themed URL.

The project demonstrates practical skills in phishing analysis, passive OSINT, IOC documentation, infrastructure mapping, incident assessment and MITRE ATT&CK mapping.

## Analyst Declaration

This project was completed for educational, defensive-security and portfolio purposes. All suspicious infrastructure used in the initial case was simulated.
