---
title: Scope and Methodology
parent: Peppol-ERDS Formal Gap Analysis
nav_order: 1
last_modified_date: YYYY-MM-DD
---

# Scope and Methodology

{: .draft }
> Draft – placeholder structure.

## Regulatory basis

The analysis is based on:

- **Regulation (EU) 2024/1183** (eIDAS 2.0), amending Regulation (EU) No 910/2014
- **Annex IV** – Requirements for qualified electronic registered delivery services
- ENISA technical guidelines on ERDS (where published)

{: .open-question }
> **Open question:** Should this analysis also cover non-qualified ERDS (Article 44) 
> or be scoped exclusively to QERDS (Annex IV)?  
> Tracked in [issue #](https://github.com/<org>/<repo>/issues/).

## Scope of Peppol capabilities assessed

The gap analysis covers:

- The Peppol four-corner message exchange model
- AS4 transport protocol as implemented under the Peppol eSENS profile
- Peppol PKI and certificate model
- Message Level Status (MLS) specification

Out of scope:

- Service Provider internal infrastructure
- National extensions to Peppol profiles

## Methodology

Each ERDS requirement is:

1. Extracted and numbered from the regulatory source
2. Mapped to a Peppol technical or governance capability (or absence thereof)
3. Classified as **Met**, **Partially met**, or **Not met**
4. Assigned a gap severity where applicable

## Conventions

| Status | Meaning |
|---|---|
| ✅ Met | Peppol satisfies this requirement as currently specified |
| 🟡 Partially met | Peppol satisfies some but not all aspects of the requirement |
| ❌ Not met | No current Peppol mechanism addresses this requirement |
| ➖ Not applicable | Requirement does not apply to Peppol's role or use case |
