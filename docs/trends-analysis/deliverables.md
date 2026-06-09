---
title: Deliverables and Next Steps
parent: Trends Analysis (D3.1)
nav_order: 9
last_modified_date: 2026-05-11
---

# Workstream 3 Scope and Deliverables

The following section outlines how this trend analysis maps to the expected deliverables 
of CIWG 2.0 Workstream 3. These deliverables are to be developed iteratively, with this 
document serving as the foundational analysis layer.

---

## Deliverable Overview

| Ref | Deliverable | Description |
|---|---|---|
| **D3.1** | Technical & Regulatory Trends Analysis (this document) | All sections — foundation for subsequent deliverables |
| **D3.2** | [Future Trust Architecture](../../future-trust-architecture/) | Future-oriented architecture informed by Pathways A, B, C and network segmentation |
| **D3.3** | [Evolution Path Assessment](../../evolution-path-assessment/) | What stays, what extends, what changes — current status vs. trends vs. implications |
| **D3.4** | [Segmentation Model](../../segmentation-model/) | Trusted lists and credential-based segments, governance model, segment examples |
| **D3.5** | Infrastructure Decisions Input | SML, dynamic discovery, regulatory alignment (QERDS, ViDA, eIDAS) |
| **D3.6** | PoC Definition and Scoping | Proof of concept scoping for high-uncertainty areas identified in D3.2–D3.4 |
| **D3.7** | [Peppol-ERDS Formal Gap Analysis](../../erds-gap-analysis/) | Structured comparison of Peppol's current architecture against ERDS requirements; identification of formal, legal, and technical gaps; assessment of the ERDS recognition path versus protocol modernisation; and OpenPeppol's recommended position |

---

## Areas Requiring Expert Input

This workstream requires input from stakeholders across the Peppol ecosystem. The 
following areas are identified as needing diverse perspectives:

**Peppol Authorities.** Experience with SP oversight, compliance assessment in different 
jurisdictions, and the practical challenges of enforcing soft law obligations.

**Service Providers.** Operational experience with the current certificate and compliance 
model, readiness for VC/attestation-based evidence, and appetite for OAuth-based 
authorisation models.

**EU Commission and standardisation bodies.** Engagement with the eIDAS 2.0 ARF 
development, EUBW technical specification work, and NIS2 implementation guidance.

---

## Immediate Next Steps

Based on this analysis, the following immediate next steps are proposed for Workstream 3:

**Validate trend analysis.** Share this document with Workstream 3 participants for 
review, challenge, and extension. Identify gaps and incorrect assumptions.

**EUBW regulatory monitoring.** Establish a watching brief on COM(2025) 838 final as 
it progresses through the legislative process. Identify key technical specification 
decisions that OpenPeppol should seek to influence.

**SML insourcing architecture review.** Engage with the SML insourcing project to 
identify integration points for trust architecture enhancements (authorisation service, 
integrity monitoring, credential-based access).

**PoC scoping — SP attestation credential.** Define the scope of a PoC for issuing and 
verifying a Peppol SP accreditation Verifiable Credential. Identify a willing Peppol 
Authority as PoC partner.

**Engage in the EUBW Expert Group on secure communication protocols.** DG CNECT is 
actively evaluating candidate transport protocols for EUBW wallet-to-wallet communication. 
OpenPeppol's participation in this expert group is essential to ensure that the Peppol 
network's architectural constraints and value propositions — the four-corner model, 
format transformation dependency, global non-EU reach, and the existing evidentiary 
framework — are represented before technical specifications are locked. Key positions 
to advance:
- The E2EE/format transformation trade-off (see [Design Tensions](design-tensions#end-to-end-encryption-vs-format-transformation-capability))
- The case for AS4 v2.0 as a PQC-ready evolution path
- The ERDS recognition framework for the four-corner model (D3.7)

---

{: .note }
> **A Note on Scope and Ambition**
>
> This workstream is not charged with redesigning Peppol. Its mandate is to examine 
> the trust model and identify where — and how — evolution is needed. Some of the 
> architectural options described in this document are medium-to-long-term possibilities. 
> The immediate priority is to develop the analytical foundation and identify the most 
> impactful near-term evolution steps that preserve optionality for the more ambitious 
> transformations. Trust is already Peppol's strongest asset. This work is about making 
> that trust explicit, portable, and ready for the next decade of operation as critical 
> infrastructure.
