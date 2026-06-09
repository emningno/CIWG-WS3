---
title: Scope and Principles
parent: Future Trust Architecture
nav_order: 1
last_modified_date: YYYY-MM-DD
---

# Scope and Principles

{: .draft }
> Draft – not yet reviewed by WS3.

## Scope

### In scope

- Trust relationships between all Peppol network participants (Service Providers, 
  end users, authorities)
- Identity and authentication mechanisms at the network boundary
- Certificate and credential lifecycle management
- Regulatory alignment with eIDAS 2.0, ViDA, and EUBW as applicable to Peppol

### Out of scope

- Internal trust mechanisms within a Service Provider's own infrastructure
- End-user authentication to Service Provider platforms (beyond interface 
  requirements)
- Peppol transport protocol internals (AS4)

---

## Architectural principles

The following principles constrain and guide the future trust architecture.
They are proposed and subject to WS3 agreement.

### P1 – Interoperability first
The architecture must preserve four-corner interoperability as its primary 
constraint. No trust mechanism may be introduced that creates bilateral 
dependencies between specific Service Providers.

### P2 – Regulatory proportionality
Requirements derived from regulation (eIDAS 2.0, ViDA, EUBW) must be 
calibrated to actual business risk. QERDS-level guarantees are not assumed 
to be required by default for all document exchange scenarios.

### P3 – Separability of concerns
Identity (who you are), authorisation (what you may do), and message 
integrity (what was sent) must be addressable independently. Architectural 
changes to one must not force changes to the others.

### P4 – Evolvability
The architecture must accommodate the introduction of verifiable credentials 
and wallet-based identity without requiring a flag-day migration of existing 
PKI infrastructure.

### P5 – Backward compatibility
Existing Service Provider accreditation and certificate infrastructure must 
remain valid through any transition period. The architecture defines a 
coexistence model, not a replacement.

---

## Constraints

_List known technical, regulatory, or governance constraints that are fixed inputs 
rather than design choices._

| Constraint | Source | Implication |
|---|---|---|
| | | |
