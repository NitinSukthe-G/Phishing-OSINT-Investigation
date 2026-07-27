# Phishing Infrastructure Analysis

## Investigation Overview

This document connects the indicators found in the simulated phishing email.

The investigation used passive OSINT and public information. No suspicious site was opened, no malicious file was downloaded and no credentials were submitted.

## Infrastructure Relationship Map

```text
Simulated Phishing Email
          |
          v
security-alert@paypa1-security.example
          |
          v
paypa1-security.example
          |
          +-- Mail Host
          |      |
          |      v
          |   mail.paypa1-security.example
          |
          +-- Source IP
          |      |
          |      v
          |   192.0.2.44
          |
          +-- Phishing URL
                 |
                 v
hxxps://paypa1-security[.]example/login
                 |
                 v
     Intended Credential-Collection Page
```

## Identified Indicators

| Indicator | Type | Relationship | Status |
|---|---|---|---|
| `security-alert@paypa1-security.example` | Email address | Simulated sender | Suspicious |
| `paypa1-security.example` | Domain | Brand-impersonation domain | Suspicious |
| `mail.paypa1-security.example` | Hostname | Simulated mail server | Suspicious |
| `192.0.2.44` | IP address | Simulated source | Documentation-only |
| `hxxps://paypa1-security[.]example/login` | URL | Phishing link | Suspicious |
| `/login` | URL path | Possible credential-collection path | Suspicious |

## Pivot Analysis

### Sender to Domain

The sender address uses `paypa1-security[.]example`, which does not match the legitimate PayPal domain.

### Domain to Mail Host

The header identifies `mail.paypa1-security[.]example`, connecting the simulated mail infrastructure to the same suspicious domain.

### Mail Host to Source IP

The source IP is `192.0.2.44`, a documentation-only address used for safe simulation.

### Domain to URL

The email sender and phishing URL use the same simulated domain, linking the delivery and credential-themed infrastructure.

### URL to Intended Objective

The `/login` path and account-verification language suggest an intended credential-theft objective.

## Email Authentication

| Control | Result | Interpretation |
|---|---|---|
| SPF | Fail | Sending server not authorised |
| DKIM | None | No cryptographic signature |
| DMARC | Fail | Authentication and alignment failed |

## Legitimate Baseline Comparison

| Characteristic | Simulated domain | Legitimate domain |
|---|---|---|
| Domain | `paypa1-security[.]example` | `paypal[.]com` |
| Spelling | Uses `1` instead of `l` | Correct spelling |
| Authentication | SPF and DMARC failed | Established infrastructure |
| DNS | No active records expected | Public DNS records |
| Certificates | None expected | Public certificate history |
| Brand relationship | None identified | Official |

## Key Findings

1. The sender domain imitates the PayPal brand.
2. The domain uses typosquatting.
3. The sender, mail host and URL share the same suspicious domain.
4. The `/login` path suggests credential collection.
5. SPF and DMARC failed.
6. No DKIM signature was present.
7. The message used urgency and account-restriction language.
8. No legitimate relationship with PayPal was identified.

## Risk Assessment

| Factor | Rating |
|---|---|
| Threat type | Credential phishing |
| Likelihood | High |
| Potential impact | High |
| Overall risk | High |
| Confidence | High |

## Detection Opportunities

- Emails containing the suspicious domain
- Messages from the simulated sender
- DNS requests for the domain
- Proxy requests containing `/login`
- Authentication attempts after email delivery
- Unusual sign-ins
- Unexpected mailbox rules
- MFA changes after possible compromise

## Recommended Containment

1. Block the sender, domain and URL.
2. Search all mailboxes for matching messages.
3. Remove matching emails.
4. Identify users who clicked the link.
5. Reset credentials and revoke sessions when required.
6. Review identity, DNS and proxy logs.
7. Notify affected users.
8. Preserve all evidence.
