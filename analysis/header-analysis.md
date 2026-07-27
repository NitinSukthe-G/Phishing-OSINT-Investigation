# Email Header Analysis

## Case Information

| Field | Value |
|---|---|
| Case type | Simulated credential-phishing investigation |
| Investigation date | 27 July 2026 |
| Analyst | Nitin Sukthe |
| Risk rating | High |
| Evidence type | Simulated |

## Sender Details

- Display name: `PayPal Security Team`
- Sender: `security-alert@paypa1-security.example`
- Return-Path: `security-alert@paypa1-security.example`
- Sending hostname: `mail.paypa1-security.example`
- Source IP: `192.0.2.44`
- Subject: `Urgent: Your account has been temporarily restricted`

## Findings

### Brand Impersonation

The display name claims to represent PayPal, but the sender domain is not the legitimate PayPal domain.

### Typosquatting

The domain `paypa1-security.example` uses the number `1` in place of the letter `l`. This is a common technique used to make a malicious domain visually resemble a trusted brand.

### SPF Failure

The header contains `spf=fail`.

This indicates that the simulated sending server was not authorised to send email for the sender domain.

### Missing DKIM Signature

The header contains `dkim=none`.

No DKIM signature was available to verify message integrity or confirm that an authorised mail system signed the email.

### DMARC Failure

The header contains `dmarc=fail`.

The message failed domain-based authentication and alignment checks.

### Suspicious Subject

The subject uses urgency and fear by claiming that the recipient's account has been restricted.

## Authentication Summary

| Control | Result | Interpretation |
|---|---|---|
| SPF | Fail | Sending server not authorised |
| DKIM | None | No cryptographic signature |
| DMARC | Fail | Authentication and alignment failed |

## Assessment

The email is classified as a **high-risk simulated phishing message**.

The strongest indicators are:

- Brand impersonation
- Typosquatting
- SPF failure
- Missing DKIM
- DMARC failure
- Urgent language
- Account-verification request
- Credential-themed URL

## Recommended Actions

1. Do not click the URL.
2. Do not reply to the sender.
3. Block the sender address and domain.
4. Search mailboxes for similar messages.
5. Search proxy and DNS logs for the domain.
6. Identify users who clicked the URL.
7. Reset credentials and revoke sessions when interaction is confirmed.
8. Preserve the original message and header as evidence.
