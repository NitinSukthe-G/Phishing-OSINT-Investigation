# Phishing URL Analysis

## Analysed URL

```text
hxxps://paypa1-security[.]example/login
```

## Safety Status

The URL is defanged:

- `hxxps` replaces `https`
- `[.]` replaces `.`
- `.example` is reserved for documentation and testing
- The URL was not opened

## URL Components

| Component | Value |
|---|---|
| Scheme | `hxxps` |
| Domain | `paypa1-security[.]example` |
| Path | `/login` |
| Parameters | None |
| Status | Simulated |

## Suspicious Characteristics

### Brand Impersonation

The domain contains a PayPal-like brand name.

### Typosquatting

The number `1` replaces the letter `l`:

- Suspicious spelling: `paypa1`
- Expected brand spelling: `paypal`

### Trust-Themed Wording

The word `security` is included to make the domain appear more trustworthy.

### Credential-Themed Path

The `/login` path suggests a page designed to imitate an account sign-in portal.

### Social-Engineering Context

The URL was delivered in an urgent message claiming that the recipient's account had been restricted.

## Risk Assessment

| Factor | Rating |
|---|---|
| Likelihood | High |
| Potential impact | High |
| Overall risk | High |
| Confidence | High |

## Assessment

The simulated URL demonstrates common phishing characteristics:

- Brand impersonation
- Typosquatting
- Credential-themed path
- Urgent social engineering
- Misleading security terminology

## Recommended Actions

1. Keep the URL defanged.
2. Block the domain and URL.
3. Search email, DNS and proxy logs.
4. Identify recipients and click activity.
5. Review authentication logs.
6. Reset credentials when interaction is confirmed.
