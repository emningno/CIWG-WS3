---
title: Technical Trends
parent: Trends Analysis (D3.1)
nav_order: 5
last_modified_date: 2026-05-11
---

# Technical Trends

The regulatory trends described in the [previous section](regulatory-trends) are enabled 
and amplified by a set of technical developments that are rapidly maturing. Understanding 
these technical trends is essential for evaluating which architectural options are realistic 
in the near, medium, and long term.

---

## Verifiable Credentials and Attestations

### The W3C VC Standard and Its Ecosystem

The W3C Verifiable Credentials Data Model (VCDM, currently at version 2.0) provides a 
standardised format for expressing claims about a subject in a way that is cryptographically 
verifiable and tamper-evident. A Verifiable Credential (VC) consists of:

- **Issuer:** The entity that makes the claim (e.g., a certification body, a Peppol Authority, a tax authority)
- **Subject:** The entity the claim is about (e.g., a service provider, a business participant)
- **Claims:** The structured assertions (e.g., "ISO 27001 certified", "Peppol SP accredited", "VAT registered in DE")
- **Proof:** The cryptographic signature that binds the claims to the issuer and allows relying parties to verify authenticity and integrity without contacting the issuer

Verifiable Presentations (VPs) allow a holder to compose selected credentials and present 
them to a verifier, with optional selective disclosure (revealing only the claims needed 
for a specific interaction). This is the technical foundation for the attestation model 
described in both the EUBW regulation and eIDAS 2.0.

### Maturity and Adoption Trajectory

The VC ecosystem has matured significantly since the W3C VCDM 1.0 specification. Key 
developments include: standardisation of credential formats (JWT-VC, SD-JWT VC, JSON-LD 
with Data Integrity Proofs); development of the DIF Presentation Exchange and OpenID for 
Verifiable Presentations (OID4VP) protocols for credential exchange; and large-scale 
pilots under the eIDAS 2.0 Architecture and Reference Framework (ARF) that are 
operationalising these standards in cross-border EU use cases.

The EU Large Scale Pilots (LSPs), with production near pilots covering business identity, 
professional qualifications, and company data, are generating practical implementation 
experience that will directly inform the EUBW's technical specifications. Peppol is 
engaged with the We Build LSP to ensure its trust architecture choices are compatible 
with emerging EU standards.

### Application to Peppol

In the Peppol context, VCs and attestations could be used in several ways:

**SP Accreditation Credentials.** Peppol Authorities (or OpenPeppol directly) could 
issue Verifiable Credentials attesting to a service provider's accredited status, valid 
scope, and jurisdiction. These credentials would be issued to the SP's Business Wallet 
and could be presented to relying parties in real-time, without querying a central Peppol 
registry.

**ISO 27001 Compliance Attestations.** Accredited certification bodies could issue VCs 
representing ISO 27001 certification status, valid scope, and expiry. These could replace 
or supplement the current certificate-document-based evidence model, enabling 
machine-readable and automatically verifiable compliance evidence.

**Participant Eligibility Credentials.** For procurement use cases, businesses could hold 
attestations of approved supplier status, financial standing, or sector-specific 
qualifications, presentable at the point of document exchange.

**Delegation Attestations.** An SP could carry attestations of its authorisation to act 
on behalf of specific business entities, with cryptographically verifiable delegation 
chains. This is particularly important for e-mandate use cases and multi-AP enterprise 
configurations.

---

## Towards Zero Trust: From Implicit to Explicit Authorisation

### The Current Model: Implicit Trust via Certificate Possession

Today's Peppol security model is, in Zero Trust terminology, a perimeter-based model: 
the network establishes a trust perimeter through PKI, and entities inside the perimeter 
(those with valid Peppol certificates) are granted broad access. Once authenticated, an 
Access Point can send and receive documents for any participant it serves.

This model does not express: which participants an SP is authorised to serve; which 
document types or processes are within scope; whether an SP is acting within or outside 
its jurisdiction; or whether delegation relationships are valid and current. The PKI 
certificate is both the identity credential and the access ticket — collapsing two 
distinct security functions.

### Zero Trust Principles Applied to the Peppol Ecosystem

Zero Trust is an architectural philosophy, not a specific technology, built on the 
principle of "never trust, always verify." Applied to the Peppol ecosystem, Zero Trust 
principles suggest:

- **Separation of authentication and authorisation:** "Who are you?" (authentication via PKI or eIDAS identity) should be distinct from "What may you do?" (authorisation via policy, attestations, and access tokens)
- **Least privilege access:** SPs should be authorised to perform only the specific functions needed for their current operation, not granted blanket access to the network
- **Continuous verification:** Access should not be permanently granted based on a point-in-time certificate issuance; authorisation should be re-evaluated at defined intervals or in response to events
- **Explicit policy enforcement:** Access decisions should be driven by explicit, machine-readable policy rather than implicit network membership

### OAuth 2.0 and OpenID Connect as Enablers

The OAuth 2.0 framework and its extensions provide a mature, widely deployed technical 
mechanism for implementing explicit, token-based authorisation. In the Peppol context, 
an OAuth-based authorisation layer could:

- Issue short-lived, scope-limited access tokens to SPs, rather than relying solely on long-lived PKI certificates
- Express authorisation scopes that capture the specific permissions granted (e.g., "send invoices on behalf of DE:VAT:123456789", "access SMP records for jurisdiction NO")
- Enable an authorisation server, operated by OpenPeppol or a federated set of PAs, to enforce policy at the point of access token issuance
- Support revocation of access in near-real-time, rather than relying on certificate revocation lists with their associated latency
- Enable delegation chains: a business entity authorising an SP to act on its behalf within explicitly defined bounds

{: .open-question }
> Implementing OAuth-based authorisation in the Peppol network is not trivial. It 
> requires an authorisation service with sufficient availability guarantees, integration 
> with the existing SML/SMP infrastructure, and careful design of the scope model. 
> These are areas for further investigation and PoC work within this workstream.

---

## Digital Wallets as Infrastructure

The Business Wallet and EU Digital Identity Wallet, as described in the EUBW regulation 
and eIDAS 2.0, are not merely storage containers for credentials. They are active 
infrastructure components that:

- Manage the lifecycle of credentials (receipt, renewal, revocation)
- Execute presentation protocols (OID4VP and related) to share credentials with relying parties
- Provide secure communication channels and digital addresses ((Q)ERDS)
- Enable qualified electronic signatures and seals within the wallet environment
- Interoperate across wallet providers and jurisdictions through common protocols defined in the ARF

For the Peppol trust architecture, wallets represent a potential shift in how compliance 
evidence is held and presented. Rather than an OpenPeppol-maintained central registry of 
certified service providers, the future model might involve SPs holding their accreditation 
credentials in their Business Wallets and presenting them on demand to relying parties — 
a decentralised, holder-centric model that reduces operational burden on OpenPeppol while 
increasing real-time verifiability.

---

## Real-Time Control Verification

A recurring theme across both the regulatory and technical trends is the move from 
point-in-time to real-time or continuous assurance. Key technical manifestations include:

**Credential status verification.** VC ecosystems include mechanisms for real-time or 
near-real-time revocation status checking (Bitstring Status List, OCSP-equivalent 
services). This enables relying parties to verify not just that a credential was issued, 
but that it remains valid at the point of use.

**Security posture telemetry.** Future iterations of the Peppol assurance model could 
include structured reporting of security events, anomalies, and control effectiveness 
metrics from SPs, moving towards a network-level security operations capability.

**SMP and SML integrity monitoring.** The SML's move into OpenPeppol's operational 
control creates an opportunity to introduce integrity monitoring for the discovery 
infrastructure — detecting anomalous registrations, modifications, or access patterns 
that could indicate compromise or fraud.

### The Data Strategy Dimension

The trust architecture's real-time assurance ambitions rest on a data foundation that 
already exists in part. OpenPeppol has established mandatory reporting requirements for 
service providers through two specifications: the Peppol End User Statistics Reporting 
(EUSR, v1.1.1) and the Peppol Transaction Statistics Reporting (TSR, v1.0.2). These 
mandated reports give OpenPeppol structured visibility into network usage: who is 
transacting, at what volumes, and on whose behalf. This provides a governance data layer 
that did not exist in the network's earlier phase.

The logical next step is to extend this model in two directions: broadening the scope of 
reportable events to include security-relevant signals (incidents, anomalies, certificate 
lifecycle events, access pattern deviations), and increasing the timeliness of reporting 
from periodic batch submissions towards near-real-time event streams where warranted by 
risk.

{: .note }
> **Data Strategy Principle**
>
> OpenPeppol already mandates structured governance reporting (EUSR, TSR) from service 
> providers — a foundation to build on, not a gap to fill from scratch. The trust 
> architecture should extend this model towards security-relevant event reporting while 
> preserving the principle that distinguishes network oversight data (legitimate governance 
> scope) from commercial and operational data (belonging to SPs and their customers). 
> The reporting framework should enable, not surveil, the ecosystem.

A critical design principle for any extension of this data capability is the distinction 
between **network oversight data** (security events, compliance status, anomaly signals, 
certificate lifecycle events — legitimately within OpenPeppol's governance mandate) and 
**commercial data** (counterparty relationships, document content, pricing — belonging to 
service providers and their customers). This boundary is not merely a privacy constraint; 
it is essential to maintaining the trust of the SP community on which the network depends.

---

## Transport Protocol Evolution and Post-Quantum Readiness

### Current Dependency: CEF eDelivery AS4 Profile v1.14

Peppol's transport layer is built on the CEF eDelivery AS4 profile, currently at version 
1.14. This profile specifies how Access Points exchange structured business documents 
using the AS4 messaging protocol — itself a profile of the OASIS ebMS3 standard — over 
SOAP/HTTP with XML-based message signatures and receipts. The cryptographic foundation 
relies on RSA and Elliptic Curve algorithms for digital signatures, with TLS providing 
transport-layer security.

This combination has proven robust and interoperable at global scale. However, it faces 
two distinct challenges: a post-quantum cryptography vulnerability that is structural and 
time-sensitive, and a growing demand from the EUBW regulatory context for end-to-end 
encryption capabilities that the current AS4 architecture does not natively support.

### Post-Quantum Cryptography Readiness

Quantum computers capable of breaking current public-key cryptographic systems (RSA, 
ECDH, ECDSA) do not yet exist at operational scale. However, the threat is not theoretical: 
"harvest now, decrypt later" attacks — where adversaries capture encrypted traffic today 
and decrypt it once quantum capability becomes available — represent a real and present 
risk for long-lived sensitive data. Business documents with multi-year legal relevance 
(contracts, invoices, procurement records) fall squarely in this category.

NIST finalised its first set of post-quantum cryptographic (PQC) standards in 2024:

| Standard | Algorithm | Purpose |
|---|---|---|
| FIPS 203 | ML-KEM | Key encapsulation |
| FIPS 204 | ML-DSA | Digital signatures |
| FIPS 205 | SLH-DSA | Stateless hash-based signatures |

The migration path for Peppol is the CEF eDelivery AS4 profile v2.0, currently in 
development by the European Commission's DIGIT unit. Version 2.0 is expected to incorporate 
PQC-ready cryptographic agility — the ability to negotiate and adopt new algorithm suites 
without requiring a full protocol replacement. OpenPeppol should actively monitor the v2.0 
specification process and engage to ensure that Peppol profile requirements are reflected 
in the new version. The transition from v1.14 to v2.0 requires a structured, time-bounded 
transition pathway rather than leaving migration to individual SP discretion.

### The Protocol Landscape

The second and more structurally significant pressure on Peppol's transport layer comes 
from signals within DG CNECT that the EUBW regulation may require or incentivise 
end-to-end encryption (E2EE) capabilities for the secure communication channels that 
wallets are required to provide. DG CNECT appears to be surveying a broad landscape of 
candidate protocols:

| Protocol | Description | B2B readiness |
|---|---|---|
| AS4 over HTTP/JSON | Modernisation of AS4 semantics onto a REST/JSON API surface, removing the SOAP envelope layer. Closest evolutionary path from the current Peppol stack | High — evolutionary |
| Signal / Sesame | Signal Protocol (X3DH + Double Ratchet) with Sesame session management. Mature for P2P messaging; adaptation to B2B non-repudiation requirements requires significant work | Low for B2B |
| DIDComm v2 | Secure, privacy-preserving messaging between parties identified by DIDs. Aligns naturally with the wallet and VC ecosystem | Medium — not yet at Peppol scale |
| Matrix with MLS | Decentralised, federated communication protocol combined with MLS (RFC 9420, IETF standard for E2EE group messaging). Post-quantum readiness roadmap | Medium — growing ecosystem |
| ActivityPub with MLS | Federated social networking protocol (W3C) with experimental E2EE via MLS. Less mature for B2B context | Low |

None of these alternatives is a drop-in replacement for AS4. Each represents a different 
set of trade-offs across implementation maturity, evidentiary strength, non-repudiation 
support, regulatory recognition, and compatibility with existing Peppol infrastructure. 
OpenPeppol's active engagement in the EUBW expert group is the primary mechanism through 
which these trade-offs can be surfaced in the regulatory process before technical 
specifications are locked.

### The Fundamental E2EE Tension

{: .warning }
> A critical architectural constraint runs through the entire protocol discussion: 
> **end-to-end encryption with sole recipient key control is structurally incompatible 
> with service provider format transformation.** If messages are encrypted from C1 to C4 
> with a key that only C4 holds, neither C2 nor C3 can read, validate, or transform the 
> message content. This would eliminate one of the core value propositions of the 
> four-corner model — format normalisation, validation, and conversion that enables 
> interoperability between business systems with different technical capabilities.

This is not a solvable problem through clever engineering within a strict E2EE model; 
it is a structural consequence of the encryption design. Resolution requires a deliberate 
architectural choice:

- E2EE is constrained to envelope and metadata layers, with message content protected hop-by-hop; or
- Format transformation is moved entirely to the sender's domain before encryption; or
- A threshold or proxy re-encryption model is introduced at significant additional complexity.

This tension must be an explicit and prominent input to OpenPeppol's engagement with DG 
CNECT and the EUBW expert group, and it connects directly to the [ERDS formal gap analysis](../../erds-gap-analysis/).
