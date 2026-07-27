# MITRE ATT&CK Mapping

## Overview

This document maps the simulated phishing investigation to the MITRE ATT&CK Enterprise framework.

Evidence status:

- **Observed:** Directly supported by the simulated evidence
- **Intended:** Suggested by the scenario but not executed
- **Not observed:** No supporting evidence

## Technique Summary

| Tactic | Technique | ID | Status | Confidence |
|---|---|---|---|---|
| Initial Access | Phishing: Spearphishing Link | T1566.002 | Observed | High |
| Execution | User Execution: Malicious Link | T1204.001 | Intended, not observed | Medium |
| Credential Access | Input Capture: Web Portal Capture | T1056.003 | Intended, not observed | Medium |

## T1566.002 — Phishing: Spearphishing Link

### Evidence

- Brand-impersonation sender
- Typosquatted domain
- Suspicious login URL
- Urgent account-restriction language
- SPF and DMARC failures
- Missing DKIM signature

### Detection Opportunities

- Newly observed or lookalike domains
- Brand-name substitutions
- Urgent account-verification language
- Sender and destination-domain mismatch
- SPF, DKIM or DMARC failures
- Multiple similar messages delivered to users

### Mitigations

- Secure email gateway
- URL analysis and rewriting
- Domain blocking
- SPF, DKIM and DMARC enforcement
- User-awareness training
- Easy phishing-reporting process

## T1204.001 — User Execution: Malicious Link

### Status

Intended but not observed.

The email attempted to persuade the recipient to click the URL, but no user click was recorded.

### Detection Opportunities

- Browser activity immediately after phishing-email delivery
- Proxy requests to low-reputation domains
- DNS requests for domains found in suspicious emails
- Endpoint activity connecting an email client to a browser

### Mitigations

- Web filtering
- Browser isolation
- Domain blocking
- Security-awareness training
- Use of saved bookmarks for important services

## T1056.003 — Input Capture: Web Portal Capture

### Status

Intended but not observed.

The `/login` path and account-verification language suggest an intended fake login portal, but the URL was not opened and no credentials were submitted.

### Detection Opportunities

- Login pages on unauthorised domains
- Password submissions to newly observed domains
- Suspicious identity-provider activity after email delivery
- Unusual sign-ins, MFA changes or password resets

### Mitigations

- Phishing-resistant MFA
- Identity-provider monitoring
- Session revocation
- Password reset when interaction is confirmed
- Domain and URL blocking

## Attack Flow

```text
T1566.002 — Spearphishing Link
             |
             v
T1204.001 — Malicious Link
             |
             v
T1056.003 — Web Portal Capture
```

## Evidence-Based Classification

| Technique | Classification | Reason |
|---|---|---|
| T1566.002 | Observed | Email contained a phishing link |
| T1204.001 | Intended | No user click observed |
| T1056.003 | Intended | No page visit or credential entry observed |

## Detection Data Sources

- Email-security logs
- DNS logs
- Proxy logs
- Endpoint telemetry
- Identity-provider logs
- Firewall logs
- Threat-intelligence platforms
- Certificate Transparency records

## Limitations

Only T1566.002 is directly supported by the simulated evidence. T1204.001 and T1056.003 represent the likely intended attack sequence.
