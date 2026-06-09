---
title: Trends Analysis (D3.1)
nav_order: 6
has_children: true
last_modified_date: 2026-05-11
---

# Technical and Regulatory Trends Shaping the Peppol Trust Model

**D3.1 — A Strategic Analysis and Foundation Document**

{: .draft }
> Status: Draft — Version 0.7 (2026-05-11). This document is the foundational analysis 
> for all subsequent WS3 deliverables. It is shared for review, challenge, and extension 
> by Workstream 3 participants.

---

## Purpose

This document provides a comprehensive analysis of the technical and regulatory trends 
bearing on the Peppol trust and security architecture. It serves as the analytical 
foundation for CIWG 2.0 Workstream 3's subsequent deliverables — the future trust 
architecture, evolution path assessment, segmentation model, and Peppol-ERDS gap analysis.

The analysis identifies two converging structural regulatory trends (the ViDA pattern 
and the eIDAS 2.0 / EUBW digital trust infrastructure), two enabling technical 
developments (verifiable credentials and Zero Trust / OAuth-based authorisation), 
and derives three complementary architectural evolution pathways and a network 
segmentation framework from their implications.

---

## Structure

| Section | Description |
|---|---|
| [Executive Summary](executive-summary) | Overview of findings and direction |
| [Vision](vision) | The five strategic capabilities the future architecture must deliver |
| [Current Trust Model](current-trust-model) | Baseline: foundations, strengths, and known gaps |
| [Regulatory Trends](regulatory-trends) | ViDA, eIDAS 2.0 / EUBW, ERDS/QERDS, NIS2, DORA, GDPR |
| [Technical Trends](technical-trends) | VCs, Zero Trust, digital wallets, real-time assurance, transport / PQC |
| [Architecture Implications](architecture-implications) | Two-layer model and three evolution pathways |
| [Network Segmentation](network-segmentation) | Segmentation mechanisms, governance model, and segment examples |
| [Design Tensions](design-tensions) | Key trade-offs the architecture must resolve |
| [Deliverables and Next Steps](deliverables) | WS3 deliverable scope and immediate next steps |
| [Annex: References](annex) | EU regulatory instruments, Peppol documents, technical standards |

---

## Version history

| Version | Date | Author | Changes |
|---|---|---|---|
| 0.2 | 2026-02-24 | RK | Initial draft. Executive summary, vision, current status, regulatory trends (ViDA, eIDAS 2.0, EUBW, NIS2, DORA, GDPR), technical trends (VCs, Zero Trust, OAuth, wallets, real-time assurance), implications and deliverables framework |
| 0.3 | 2026-03-10 | RK | Added Section 3.2.6 on ERDS/QERDS and qualification of transport services, including proportionality analysis and market impact assessment. Corrected affiliation to OpenPeppol Operating Office. Extended Annex references |
| 0.4 | 2026-03-17 | RK | Added Section 5.3 on network segmentation (credential-based and trusted list mechanisms, complementary architecture, segment examples). Sharpened liberal inner security framing. Added end-user KYC gap. Added data strategy dimension with EUSR/TSR context. Added segmentation vs. interoperability design tension |
| 0.5 | 2026-03-24 | RK | Added four architectural illustrations (SVG source files produced) |
| 0.6 | 2026-04-14 | RK | Incorporated feedback from CIWG 2.0 WS3 meeting of 31 March. Nuanced data strategy section to reflect existing EUSR/TSR reporting as foundation. Minor editorial corrections |
| 0.7 | 2026-05-11 | RK | Added Section 4.5 on transport protocol evolution and post-quantum cryptography readiness (AS4 v1.14 → v2.0, NIST PQC standards, DG CNECT protocol landscape for EUBW, E2EE design tension). Added D3.7 (Peppol-ERDS Formal Gap Analysis) to deliverables. Added EUBW Expert Group engagement to next steps. Extended Annex A.3 |
