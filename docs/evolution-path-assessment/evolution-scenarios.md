---
title: Evolution Scenarios
parent: Evolution Path Assessment
nav_order: 2
last_modified_date: YYYY-MM-DD
---

# Evolution Scenarios

{: .draft }
> Draft – scenario descriptions are placeholders.

Three scenarios are assessed. They are intended as analytically distinct 
archetypes, not necessarily mutually exclusive paths. The recommended path 
may draw on elements of more than one.

---

## Scenario A – Incremental PKI hardening

_Minimal structural change. Strengthen the existing PKI model to meet 
regulatory requirements without introducing new identity paradigms._

**Key characteristics:**
- Peppol CA remains the sole root of trust
- Certificate profiles updated to meet eIDAS 2.0 requirements where applicable
- No verifiable credentials or wallet integration

**Assumptions:**
- Regulatory requirements can be met by PKI alone
- Ecosystem appetite for structural change is low

---

## Scenario B – Parallel VC layer

_Introduce verifiable credentials as an optional, additive trust layer 
alongside existing PKI. Mandatory for specific high-assurance scenarios._

**Key characteristics:**
- Peppol PKI retained for base-level trust
- VC issuance by Peppol Authorities (or accredited issuers) for higher-assurance roles
- EUBW interaction at the VC layer only

**Assumptions:**
- VC infrastructure mature enough for production by target date
- Ecosystem can operate in dual-mode for a transition period

---

## Scenario C – Trust model convergence

_Deeper integration with the EU digital identity ecosystem, positioning Peppol 
as a trust scheme within eIDAS 2.0 / EUBW frameworks._

**Key characteristics:**
- Peppol Authorities act as qualified trust service providers or relying parties
- Participant identity anchored in EUDI Wallet / EUBW
- Peppol PKI scoped to network-layer trust only

**Assumptions:**
- EUBW regulation and ecosystem sufficiently mature
- Peppol governance can accommodate eIDAS-aligned trust scheme status

---

{: .open-question }
> **Open question:** Should the scenario set include a fourth scenario 
> representing deliberate non-action (status quo preservation beyond 
> compliance minimum)?  
> Tracked in [issue #](https://github.com/<org>/<repo>/issues/).
