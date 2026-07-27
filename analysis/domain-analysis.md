# Domain and DNS Analysis

## Investigated Domain

```text
paypa1-security[.]example
```

## Scope

The domain is part of a simulated phishing investigation. It was not opened in a browser and was not actively scanned.

## DNS Checks Performed

- A
- AAAA
- MX
- NS
- PTR / reverse DNS

No active DNS records were expected because `.example` is reserved for documentation and testing.

## WHOIS Findings

No normal registration record was expected for the simulated `.example` domain.

## Source IP Findings

The simulated source IP was:

```text
192.0.2.44
```

This address is used for documentation and does not represent a real attacker-controlled server.

## Infrastructure Summary

| Item | Finding |
|---|---|
| Domain | Simulated |
| DNS records | No active records expected |
| WHOIS registration | No normal registration expected |
| Hosting provider | Not applicable |
| Mail server | Simulated |
| Source IP | Documentation-only |
| Reverse DNS | No meaningful result expected |

## Suspicious Domain Characteristics

1. PayPal brand impersonation
2. Letter-to-number substitution
3. Addition of the word `security`
4. Credential-themed `/login` path
5. Connection to an urgent account-verification message

## Analyst Assessment

The lack of active infrastructure is expected because the case uses reserved test data. The domain structure still demonstrates realistic phishing and typosquatting patterns.

## Recommended Actions

1. Block the domain in email and web-security controls.
2. Search email logs for the domain.
3. Search DNS and proxy logs for access attempts.
4. Monitor newly registered domains similar to the organisation's brand.
5. Preserve DNS and WHOIS results as evidence.
