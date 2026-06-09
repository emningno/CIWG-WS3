---
title: Vision
parent: Trends Analysis (D3.1)
nav_order: 2
last_modified_date: 2026-05-11
---

# Vision

## What We Are Working Towards

The vision for Peppol's trust and security architecture is not to replace what works, 
but to make explicit what has so far been implicit, and to make durable what has so far 
been fragile in the face of a more complex regulatory and technical environment.

{: .note }
> **Vision Statement**
>
> Peppol's trust model should evolve from a network built on contractual obligations and 
> certificate possession towards an ecosystem where trust is explicit, portable, auditable 
> in real time, and aligned with emerging EU and global digital trust and regulatory 
> frameworks, without losing the network's openness, flexibility, and global reach.

This vision rests on five strategic capabilities that the future trust architecture should deliver.

---

## Five Strategic Capabilities

### 1. Explicit Trust

Today, many trust decisions in the Peppol network are implicit. The possession of a valid 
Peppol certificate is treated as both authentication and authorisation: if you have the 
certificate, you can participate. The next phase of Peppol's trust model should make trust 
decisions explicit: who may do what, on behalf of whom, under which conditions, and with 
which verifiable evidence.

### 2. Portable Compliance Evidence

Peppol Authorities and OpenPeppol currently require service providers to demonstrate 
compliance through a mix of contractual assertions and periodic certifications. The future 
architecture should allow compliance evidence — such as ISO 27001 certification status, 
regulatory accreditations, or qualified trust service provider status — to be carried in 
standardised, verifiable formats, reducing administrative burden while increasing 
reliability. Verifiable credentials and attestations issued by authoritative issuers and 
stored in wallets provide the technical mechanism for this.

### 3. Graduated and Context-Aware Authorisation

Not all actors in the Peppol network have the same role, risk profile, or regulatory 
context. A future architecture should support graduated authorisation: different access 
levels, delegation chains, and operational permissions should be expressible and 
enforceable, rather than defaulting to a binary certified/not-certified status. This is 
particularly important as Peppol is mandated for fiscal and administrative use cases where 
accountability matters.

### 4. Regulatory Alignment Without Regulatory Capture

Peppol's value as a global, member-based, open network must be preserved. The trust 
architecture should be designed to align with EU regulatory requirements (eIDAS 2.0, EUBW, 
NIS2, DORA, ViDA) where they add value, but must avoid designing itself as purely an 
instrument of any single regulatory regime. Peppol serves actors across jurisdictions; 
the architecture must remain workable outside the EU as well as within it.

### 5. Real-Time Assurance

The current assurance model is predominantly point-in-time: a certificate is valid, a 
surveillance audit was passed, a contract was signed. As Peppol is increasingly mandated 
for real-time fiscal reporting and as regulatory frameworks like NIS2 impose continuous 
risk management obligations, the trust architecture should evolve towards continuous 
assurance capabilities — real-time or near-real-time verification of security posture 
and credential validity, rather than relying solely on annual review cycles.

---

## What This Vision Does Not Mean

| We are NOT proposing to... | We ARE exploring how to... |
|---|---|
| Redesign Peppol from scratch or replace the four-corner model | Make authorisation explicit and policy-driven |
| Mandate eIDAS qualification for all actors globally | Leverage EU trust infrastructure where it adds value |
| Impose breaking changes on current service providers | Enable verifiable compliance evidence at scale |
| Replace PKI-based transport security in the near term | Evolve the network's security posture in a structured, risk-proportionate way |
