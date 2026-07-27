# Phishing Investigation Timeline

## Overview

This timeline reconstructs the simulated credential-phishing incident using:

- Email-header timestamps
- Email content
- Authentication results
- URL analysis
- Passive OSINT findings
- Analyst activity

## Event Timeline

| Date and Time | Event | Evidence | Status |
|---|---|---|---|
| 27 July 2026, 09:09:40 IST | Simulated phishing email created | Date header | Confirmed in scenario |
| 27 July 2026, 09:10:25 IST | Email received by simulated mail server | Received header | Confirmed |
| 27 July 2026, 09:10:25 IST | SPF failed | Received-SPF | Confirmed |
| 27 July 2026, 09:10:25 IST | DKIM signature absent | Authentication-Results | Confirmed |
| 27 July 2026, 09:10:25 IST | DMARC failed | Authentication-Results | Confirmed |
| 27 July 2026, 09:11:00 IST | Recipient received urgent restriction message | Email body | Simulated |
| 27 July 2026, 09:11:00 IST | Recipient was instructed to visit login URL | Email body | Simulated |
| 27 July 2026, 09:15:00 IST | Email reported for investigation | Scenario | Simulated |
| 27 July 2026, 09:20:00 IST | Header and URL indicators extracted | Analyst activity | Confirmed |
| 27 July 2026, 09:30:00 IST | DNS and WHOIS review completed | Evidence files | Confirmed |
| 27 July 2026, 09:45:00 IST | Passive OSINT checks completed | OSINT notes | Confirmed |
| 27 July 2026, 10:00:00 IST | Infrastructure relationships documented | Analysis | Confirmed |
| 27 July 2026, 10:15:00 IST | Email classified as credential phishing | Assessment | Confirmed |

## Reconstructed Attack Flow

```text
Brand-Impersonation Email Prepared
              |
              v
Typosquatted Sender Domain Used
              |
              v
Email Delivered
              |
              v
SPF and DMARC Fail
              |
              v
Urgent Account-Restriction Message
              |
              v
Recipient Directed to Login URL
              |
              v
Intended Credential Collection
              |
              v
Email Reported and Investigated
```

## Confirmed Findings

- Typosquatted sender domain
- SPF failure
- Missing DKIM
- DMARC failure
- Urgent login request
- Same domain used by sender and URL
- Documentation-only source IP

## Not Observed

- User click
- Credential submission
- Malware execution
- File download
- Account compromise
- Data theft
- Contact with real attacker infrastructure

## Incident Classification

| Category | Assessment |
|---|---|
| Incident type | Credential phishing |
| Delivery method | Email |
| Intended target | Account credentials |
| Likelihood | High |
| Impact | High |
| Overall risk | High |
| Confidence | High |

## Recommended Response Timeline

| Priority | Action |
|---|---|
| Immediate | Block sender, domain and URL |
| Immediate | Search mailboxes for matching messages |
| Immediate | Identify recipients and possible clicks |
| Within 1 hour | Remove matching messages |
| Within 1 hour | Reset credentials when interaction is confirmed |
| Within 1 hour | Revoke suspicious sessions |
| Within 4 hours | Review DNS, proxy and identity logs |
| Within 24 hours | Notify affected users |
| Within 24 hours | Update detection rules |
| Within 48 hours | Complete lessons learned |
