# Reputation and Certificate Analysis

## Scope

Passive OSINT searches were performed using:

- VirusTotal
- urlscan.io
- crt.sh

No suspicious URL was opened directly, no file was uploaded and no new scan was submitted.

## Investigated Domains

| Domain | Purpose |
|---|---|
| `paypa1-security[.]example` | Simulated phishing domain |
| `paypal[.]com` | Legitimate baseline |

## VirusTotal Findings

### Simulated Domain

No meaningful reputation history was expected because the domain is simulated.

The absence of a public report does not prove that a domain is safe. Newly created malicious infrastructure may have little or no reputation history.

### Legitimate Baseline

The legitimate domain showed established public reputation, categorisation and historical analysis information.

Exact results may change over time and should be supported by the screenshots captured during the investigation.

## urlscan.io Findings

### Simulated Domain

No historical results were expected for the simulated domain.

### Legitimate Baseline

Existing public scans showed established internet infrastructure associated with the legitimate organisation.

No new scan was submitted.

## Certificate Transparency Findings

### Simulated Domain

No certificate history was expected for the simulated `.example` domain.

### Legitimate Baseline

Certificate Transparency records showed certificates associated with the legitimate domain and authorised subdomains.

## Comparison

| Characteristic | Simulated domain | Legitimate baseline |
|---|---|---|
| Brand spelling | Misspelled | Correct |
| Public reputation | None expected | Established |
| Historical scans | None expected | Existing public records |
| Certificate history | None expected | Established |
| Brand relationship | None identified | Official |

## Important Limitation

Public threat-intelligence sources may not contain complete or current information. Findings should be correlated with email headers, DNS logs, proxy logs and identity-provider activity.

## Analyst Assessment

The passive OSINT findings support the earlier email-header and URL analysis. The simulated domain demonstrates brand impersonation and typosquatting, while the legitimate baseline shows established public infrastructure.
