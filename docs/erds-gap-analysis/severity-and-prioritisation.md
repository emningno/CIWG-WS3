---
title: Severity and Prioritisation
parent: Peppol-ERDS Formal Gap Analysis
nav_order: 5
last_modified_date: YYYY-MM-DD
---

# Severity and Prioritisation

{: .draft }
> Draft – severity ratings are placeholders.

## Severity classification

| Severity | Definition |
|---|---|
| **Critical** | Gap prevents compliance with a mandatory legal obligation with no available workaround |
| **Significant** | Gap represents a material non-compliance but can be addressed by architectural or policy change |
| **Minor** | Gap is marginal or can be mitigated through interpretation or existing mechanisms |

## Gap severity summary

| Req # | Requirement summary | Status | Severity | Notes |
|---|---|:---:|---|---|
| QERDS-01 | Provided by qualified TSP | ❌ | Critical | Structural — not addressable without Peppol Authority qualifying as TSP |
| QERDS-04 | Qualified electronic seal | ❌ | Critical | |
| QERDS-06 | Qualified timestamp | ❌ | Significant | Addressable by integration with QTSP |
| QERDS-07 | Trusted third-party record | ❌ | Significant | |
| ERDS-04 | Date/time of sending/receiving | 🟡 | Minor | MLS partially satisfies; QTS would close |
