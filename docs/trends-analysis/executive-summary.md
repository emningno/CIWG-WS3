---
title: Executive Summary
parent: Trends Analysis (D3.1)
nav_order: 1
last_modified_date: 2026-05-11
---

# Executive Summary

OpenPeppol operates a global, member-based business document network built on a four-corner 
model and governed primarily through soft law — contractual agreements, PKI certificates, 
and accreditation frameworks. This model has been highly effective during the network's 
growth phase. However, the operating environment is shifting in ways that require deliberate 
architectural reassessment.

## Two converging regulatory trends

Two major and structurally distinct regulatory trends are now converging on the Peppol 
ecosystem:

**The ViDA trend.** Regulation is increasingly mandating the use of trusted network 
ecosystems like Peppol for fiscal reporting purposes (e-reporting, VAT). This creates 
value and legitimacy for the Peppol network, but also introduces new actors, expanded 
models (5-corner and 6-corner architectures), and regulatory compliance requirements on 
service providers that Peppol's soft law cannot fully address alone.

**The Digital Trust trend.** The EU's eIDAS 2.0 framework and the proposed European 
Business Wallet (EUBW) regulation are establishing a new digital trust infrastructure 
based on verifiable credentials, attestations, and digital identity wallets. This enables 
richer, more portable, and more auditable trust relationships across the EU — and 
potentially globally — in ways that are directly relevant to how Peppol governs access, 
delegation, and compliance.

## Two enabling technical developments

On the technical side, two parallel developments are enabling a transition from Peppol's 
current implicit, certificate-based trust model towards more explicit and verifiable forms 
of access control and governance:

**Verifiable Credentials (VCs) and attestations** are becoming technically mature and 
standardised, enabling proof of compliance, role, mandate, and qualification to be 
carried, shared, and verified without relying on a central registry.

**Zero Trust and token-based authorisation** (OAuth 2.0 / OpenID Connect) offer an 
architectural alternative to today's implicit access model, where possession of a Peppol 
certificate grants broad network access. These models allow fine-grained, context-aware 
authorisation that can be more robustly audited and revoked.

## Current status

The current status of Peppol's trust architecture reflects a deliberate first step: 
ISO/IEC 27001 certification has been introduced as the baseline security assurance 
requirement for service providers. Real-time control verification remains an aspirational 
goal rather than a current capability.

## Scope of this document

This document provides a comprehensive analysis of these trends and their implications. 
It is intended as the foundational analysis for CIWG 2.0 Workstream 3 deliverables, 
including the future-oriented trust and security architecture, identification of evolution 
paths, and input to key decisions on topics such as SML federation, dynamic discovery, 
and regulatory alignment.
