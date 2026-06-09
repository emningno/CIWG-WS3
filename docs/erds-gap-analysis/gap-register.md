---
title: Gap Register
parent: Peppol-ERDS Formal Gap Analysis
nav_order: 4
last_modified_date: YYYY-MM-DD
---

# Gap Register

{: .draft }
> Draft – assessments are placeholders. To be completed in WS3.

Each row maps one ERDS/QERDS requirement to the current Peppol capability 
and states the resulting gap. See [Scope and Methodology](scope-and-methodology) 
for status and severity definitions.

## Non-qualified ERDS (Article 44)

| Req # | Requirement summary | Peppol capability | Status | Gap description |
|---|---|---|:---:|---|
| ERDS-01 | Sender identification | SP certificate / accreditation | 🟡 | |
| ERDS-02 | Addressee identification before delivery | SMP lookup | 🟡 | |
| ERDS-03 | Data integrity | AS4 message signing | ✅ | |
| ERDS-04 | Date and time of sending/receiving | AS4 timestamp + MLS | 🟡 | Timestamp is sender-generated; no qualified timestamp |
| ERDS-05 | Protection against loss/theft/alteration | TLS + message signing | 🟡 | |

## Qualified ERDS (Annex IV)

| Req # | Requirement summary | Peppol capability | Status | Gap description |
|---|---|---|:---:|---|
| QERDS-01 | Provided by qualified TSP | No Peppol mechanism | ❌ | Peppol Authorities are not qualified TSPs |
| QERDS-02 | Sender identity at high LoA | SP cert (no LoA mapping) | 🟡 | |
| QERDS-03 | Addressee identity verified | SMP (no verification step) | ❌ | |
| QERDS-04 | Qualified electronic seal | No current mechanism | ❌ | |
| QERDS-05 | Alteration detectability | AS4 signing | ✅ | |
| QERDS-06 | Qualified timestamp | No current mechanism | ❌ | |
| QERDS-07 | Trusted third-party record | No current mechanism | ❌ | |
