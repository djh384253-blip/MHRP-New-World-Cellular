# 02 — MHRP SDR Replacement Architecture

**Status:** Design proposal / concept. Not implemented. Not tested.  
**Version:** 0.1-draft  
**Date:** TBD  
**Authors:** TBD  
**Reviewers:** TBD  

## Related documents

- [01 — MHRP System Specification](01_MHRP_System_Specification.md)
- [03 — MHRP Engineering Master Roadmap](03_MHRP_Engineering_Master_Roadmap.md)
- [04 — MHRP Theoretical Frameworks](04_MHRP_Theoretical_Frameworks.md)
- [05 — MHRP Sovereign Boot Image Instructions](05_MHRP_Sovereign_Boot_Image_Instructions.md)

---

## 1. Purpose, Scope, and Non-Goals

### 1.1 Purpose

This document proposes a conceptual architecture for a possible replacement for, or alternative to, a conventional software-defined radio (SDR) within the MHRP / New World Cellular architecture.

Its purpose is to define the questions, boundaries, requirements, assumptions, constraints, review gates, and validation approach that would need to be addressed before implementation work could be responsibly planned.

This document does not establish a completed design, a deployable system, an approved product, or a tested radio platform.

### 1.2 Scope

This document covers architecture-level planning for:

- Purpose, scope, terminology, and non-goals.
- Relationship to the broader MHRP system architecture.
- Functional and non-functional requirements that remain subject to review.
- Assumptions, constraints, and unresolved dependencies.
- Threat-model, legal, regulatory, safety, and compliance questions.
- Hardware-platform assumptions at a general class level only.
- The proposed boundary between RF, baseband, modem, firmware, and host software responsibilities.
- Proposed protocol, control-plane, data-plane, and host-interface questions.
- Timing, synchronization, clocking, security, privacy, observability, diagnostics, power, thermal, and physical constraints.
- Testing, validation, verification, failure handling, migration, coexistence, and prototype planning.
- Open questions and future decision records.

### 1.3 Non-Goals

This document is not:

- Source code, firmware, a boot image, or a build system.
- A hardware schematic, board design, bill of materials, or parts-selection document.
- A claim that an SDR replacement exists, works, or has been tested.
- A claim that any frequency, spectrum, radio service, radio standard, modem standard, network, or telecommunications infrastructure is supported.
- A runtime configuration file.
- Authorization to transmit on any spectrum or operate any radio equipment.
- A statement of legal approval, certification, regulatory compliance, safety approval, export-control clearance, or standards conformance.
- A substitute for engineering, security, legal, regulatory, certification, safety, or field-test review.

Runtime configuration, if it becomes relevant after a specific implementation exists, is out of scope for this document. The file `cell_config.cfg` is not a design-document location.

---

## 2. Terminology and Acronyms

| Term | Definition | Status |
| --- | --- | --- |
| MHRP | TBD. This term must be aligned with `01_MHRP_System_Specification.md`. | Assumption |
| SDR | Software-defined radio. | General term |
| SDR replacement | A proposed alternative or replacement architecture for functions conventionally associated with an SDR. | Proposal |
| RF | Radio-frequency domain. | General term |
| Baseband | Signal-processing domain before or after RF conversion, depending on implementation. | General term |
| Modem | Subsystem responsible for modulation and demodulation functions. | General term |
| Control plane | Interfaces and processes responsible for configuration, coordination, identity, and management. | Proposed terminology |
| Data plane | Interfaces and processes responsible for carrying application or network payload data. | Proposed terminology |
| TBD | To be determined through review and documented decision-making. | Placeholder |

Terminology must be reconciled with the existing MHRP system specification and theoretical-framework documents before it is treated as authoritative.

---

## 3. Relationship to MHRP System Architecture

This document describes a proposed subsystem or architectural option within the broader MHRP system.

- System-level requirements and terminology must remain aligned with `01_MHRP_System_Specification.md`.
- Any future engineering sequencing or implementation milestones must be reflected in `03_MHRP_Engineering_Master_Roadmap.md` only after review and approval.
- This document does not supersede the system specification, roadmap, theoretical framework, or sovereign boot-image instructions.
- This document does not establish that MHRP requires a full replacement of conventional SDR technology. Whether the proposed architecture replaces, supplements, or coexists with conventional SDR remains an open decision.

Open questions include:

- Which system-level interfaces must this proposed subsystem expose?
- Which requirements are mandatory, optional, or out of scope?
- Whether the MHRP architecture requires a replacement, an alternative, a supplement, or continued use of conventional SDR components.
- Which documents are authoritative for system requirements, security requirements, and engineering sequencing.

---

## 4. Requirements

### 4.1 Functional Requirements

The following are proposed requirements. They are not approved implementation requirements until reviewed.

| ID | Proposed requirement | Status |
| --- | --- | --- |
| FR-01 | Support modulation and demodulation functions required by the eventually approved MHRP architecture. | TBD |
| FR-02 | Support an approved timing and synchronization approach. | TBD |
| FR-03 | Expose approved host, control-plane, and data-plane interfaces. | TBD |
| FR-04 | Support approved identity, security, and key-management functions. | TBD |
| FR-05 | Support approved failure detection, degradation, recovery, and rollback behavior. | TBD |
| FR-06 | Support observability and diagnostics consistent with approved privacy and security constraints. | TBD |
| FR-07 | Support validation through simulation and laboratory methods before any field evaluation is considered. | Proposal |

### 4.2 Non-Functional Requirements

The following are architecture goals or requirements to be prioritized through review.

| ID | Proposed requirement | Status |
| --- | --- | --- |
| NFR-01 | The design should be testable in simulation and in a controlled laboratory environment. | Proposal |
| NFR-02 | The design should define observable behavior without unnecessarily exposing sensitive data or metadata. | Proposal |
| NFR-03 | The design should identify maintainability, reviewability, and documentation requirements. | Proposal |
| NFR-04 | The design should identify power, thermal, physical, supply-chain, and lifecycle constraints. | TBD |
| NFR-05 | The design should support staged validation rather than unsupported deployment claims. | Proposal |
| NFR-06 | The design should identify legal, regulatory, certification, safety, and compliance dependencies before any transmission or field deployment is considered. | Constraint |

### 4.3 Assumptions and Constraints

#### Assumptions

- Hardware classes appropriate to an eventual implementation may be available, but no specific hardware is selected by this document.
- System, security, legal, regulatory, and engineering review will occur before implementation claims are made.
- The eventual architecture may need to coexist with or interoperate with conventional SDR-based components, but no compatibility is claimed.
- Existing MHRP documents provide the initial context but require reconciliation before they are treated as a complete set of implementation requirements.

#### Constraints

- No transmission, spectrum use, field deployment, or compliance claim may be inferred from this document.
- No runtime configuration values are defined by this document.
- No particular radio frequency, channel bandwidth, duplexing method, modulation, waveform, range, data rate, latency, or protocol is assumed to be approved.
- No security guarantee, privacy guarantee, certification, or standards conformance is claimed.
- All future work must remain subject to applicable law, regulation, licensing, certification, safety, export-control, and security-review requirements.

---

## 5. Threat Model, Legal, and Regulatory Constraints

**Status:** Open questions requiring qualified legal, regulatory, security, engineering, and safety review.

This section identifies categories that require review. It does not establish compliance or authorization.

### 5.1 Threat-model topics

Potential threat categories to assess include:

- Local RF interference and environmental interference.
- Intentional jamming or denial-of-service conditions.
- Spoofing, replay, impersonation, and identity compromise.
- Compromise of host systems, firmware, software, keys, credentials, or update channels.
- Supply-chain, component-integrity, and maintenance risks.
- Physical tampering, theft, environmental damage, overheating, or power interruption.
- Privacy risks associated with metadata, identifiers, logs, diagnostics, location information, and telemetry.

### 5.2 Legal, regulatory, and compliance topics

The following require review before any implementation or deployment decision:

- Applicable jurisdictions.
- Spectrum-access and licensing requirements.
- Equipment authorization, certification, and electromagnetic-compatibility requirements.
- Safety requirements.
- Export-control and encryption-control considerations.
- Data-protection and privacy requirements.
- Intellectual-property, dependency-license, and AGPL-3.0 implications.

No claim of lawful operation, certification, authorization, compliance, or approval is made by this document.

---

## 6. Hardware Assumptions and Platform Envelope

**Status:** Assumptions and open questions only. No hardware part numbers or validated platform selections are specified.

The eventual design may require decisions regarding:

- RF front-end class.
- Analog-to-digital and digital-to-analog conversion class.
- Baseband-compute class.
- Hardware acceleration, programmable-logic, firmware, and host-software boundaries.
- Clocking and synchronization source class.
- Power-source class.
- Thermal-management approach.
- Enclosure, environmental, and physical-security class.
- Storage, memory, update, maintenance, and supply-chain constraints.

All hardware decisions remain TBD. Selection criteria must be defined before component choices are proposed.

---

## 7. RF, Baseband, and Modem Boundary

**Status:** Conceptual proposal.

The eventual architecture must define:

- Where analog RF processing begins and ends.
- Where digital baseband processing begins and ends.
- Which functions are fixed hardware, configurable hardware, firmware, host software, or external services.
- Where modem responsibilities reside.
- Which interfaces cross trust, timing, or safety boundaries.
- How changes to one layer affect testing, security, maintenance, recoverability, and interoperability.

No specific implementation boundary is committed by this document.

---

## 8. Protocol and Network Interfaces

**Status:** Proposal and open questions.

The eventual design must identify and review:

- Host interface requirements.
- Control-plane interfaces.
- Data-plane interfaces.
- Internal bus or interconnect requirements.
- Discovery, routing, identity, session, and management interfaces.
- Configuration, status, diagnostics, failure, and recovery signaling.
- Interoperability boundaries with MHRP components and any conventional SDR-based components.

No claim is made that the proposed architecture is compatible with any named cellular, wireless, satellite, public-safety, commercial, or other radio standard or network.

---

## 9. Timing, Synchronization, and Clocking

**Status:** Proposal and open questions.

The eventual design must address:

- Time-base requirements.
- Synchronization source options.
- Whether it depends on, can operate without, or can fall back from external time sources.
- Holdover behavior.
- Clock-loss detection.
- Resynchronization behavior.
- Timing-related failure handling.
- Validation methods for timing and synchronization assumptions.

No accuracy, stability, holdover, or synchronization-performance figures are stated or implied by this document.

---

## 10. Security and Privacy Architecture

**Status:** Proposal and open questions. No algorithms, guarantees, or completed security properties are committed here.

The eventual architecture must define and review:

- Trust boundaries.
- Identity model.
- Credential and key-management lifecycle.
- Enrollment, rotation, revocation, recovery, and compromise response.
- Secure-boot, measured-boot, update, and rollback assumptions where applicable.
- Cryptographic-agility requirements.
- Metadata-protection goals.
- Logging, diagnostics, telemetry, and data-retention privacy constraints.
- Threat-model linkage and security-validation approach.

No security guarantee, privacy guarantee, anonymity property, resistance claim, or cryptographic property is established by this document.

---

## 11. Observability, Diagnostics, and Telemetry

**Status:** Proposal and open questions.

The eventual design must define:

- What events, metrics, logs, and diagnostics are needed.
- Which actors may access diagnostics.
- Retention, deletion, access-control, and audit requirements.
- Data minimization and redaction requirements.
- Whether telemetry is optional, mandatory, local-only, or externally transmitted.
- How field failures may be captured without creating unnecessary privacy or security risk.
- How observability remains available during partial failures or degraded operation.

No privacy-preserving behavior is claimed until a reviewed design and validation evidence exist.

---

## 12. Power, Thermal, and Physical Constraints

**Status:** Assumptions and open questions.

The eventual design must identify:

- Power-source assumptions and operating-envelope requirements.
- Power budgeting needs.
- Thermal constraints and cooling assumptions.
- Enclosure and environmental constraints.
- Physical-security, tamper, maintenance, and serviceability requirements.
- Transport, installation, and lifecycle-management constraints.

No numeric power, thermal, environmental, durability, reliability, or operating-life values are stated or implied by this document.

---

## 13. Testing, Validation, and Verification

**Status:** Proposal.

Before implementation claims are made, an eventual design should define a staged validation plan that may include:

- Architecture review.
- Threat-model and security review.
- Legal, regulatory, safety, and compliance review where relevant.
- Simulation.
- Controlled laboratory evaluation.
- Interface and failure-mode testing.
- Documentation review and requirement traceability.
- Acceptance criteria.
- Reproducibility and evidence-retention requirements.

Any consideration of field evaluation must occur only after the relevant legal, regulatory, safety, engineering, and security reviews have been completed.

No testing has been performed or results reported by this document.

---

## 14. Failure Modes, Degradation, and Recovery

**Status:** Proposal and open questions.

The eventual design should define expected detection, degradation, containment, recovery, reporting, and rollback behavior for at least:

- Interference.
- Jamming or denial-of-service conditions.
- Spoofing, replay, or impersonation attempts.
- Identity, credential, or key compromise.
- Power interruption.
- Clock loss or synchronization loss.
- Overheating or thermal limitations.
- Partial hardware, firmware, software, storage, or interface failure.
- Update failure or rollback need.
- Telemetry, logging, or diagnostic failure.

No guarantee of graceful degradation, resilience, recovery time, safety outcome, or availability is made by this document.

---

## 15. Migration, Interoperability, and Coexistence with Conventional SDR

**Status:** Proposal and open questions.

The eventual design must determine:

- Whether the architecture replaces, supplements, or coexists with conventional SDR components.
- Which interfaces or behaviors must remain compatible.
- Whether migration is incremental, optional, or all-at-once.
- How rollback is performed if a future implementation does not meet approval gates.
- What dependencies, documentation, test evidence, or operational changes would be required.

No drop-in replacement, interoperability, backward compatibility, migration path, or rollback capability is claimed.

---

## 16. Prototype Phases and Engineering Plan

**Status:** Proposal only. These are not approved roadmap commitments or implementation milestones.

A possible review-gated progression is:

| Phase | Proposed focus | Required outcome before proceeding |
| --- | --- | --- |
| Phase 0 | Requirements, terminology, scope, threat model, and legal/regulatory question inventory. | Reviewed requirements and identified owners for open questions. |
| Phase 1 | Architecture review and simulation planning. | Reviewable architecture artifacts and documented simulation assumptions. |
| Phase 2 | Controlled laboratory prototype planning and validation design. | Approved test plan, safety constraints, and evidence requirements. |
| Phase 3 | Any future controlled evaluation, if appropriate. | Explicit engineering, legal, regulatory, safety, and security approval. |
| Phase 4 | Any future field evaluation, if appropriate. | Explicit approval, validated evidence, and applicable legal/regulatory authorization. |

No phase is authorized merely by its inclusion in this document. Any future implementation milestone must be separately reviewed and added to `03_MHRP_Engineering_Master_Roadmap.md` only after approval.

---

## 17. Open Questions and Decision Log

### 17.1 Open questions

| ID | Question | Owner | Status |
| --- | --- | --- | --- |
| OQ-01 | What is the intended spectrum and applicable regulatory domain? | TBD | Open |
| OQ-02 | What are the eventual band, bandwidth, duplexing, modulation, waveform, range, data-rate, latency, and reliability requirements? | TBD | Open |
| OQ-03 | What antenna, link-budget, coexistence, interference, and environmental assumptions apply? | TBD | Open |
| OQ-04 | What hardware-platform, supply-chain, lifecycle, and maintenance constraints apply? | TBD | Open |
| OQ-05 | What is the approved RF/baseband/modem boundary? | TBD | Open |
| OQ-06 | What host, network, control-plane, data-plane, discovery, routing, and management interfaces are required? | TBD | Open |
| OQ-07 | What timing, synchronization, external-time-source, holdover, and clock-loss behavior is required? | TBD | Open |
| OQ-08 | What identity, key-management, secure-boot, update, cryptographic-agility, privacy, and metadata-protection requirements apply? | TBD | Open |
| OQ-09 | What observability, logging, telemetry, retention, redaction, and diagnostic requirements apply? | TBD | Open |
| OQ-10 | What power, thermal, enclosure, environmental, transport, and physical-security constraints apply? | TBD | Open |
| OQ-11 | What simulation, laboratory, safety, verification, test-evidence, and acceptance criteria are required? | TBD | Open |
| OQ-12 | What behavior is required under interference, jamming, spoofing, power loss, clock loss, overheating, partial failure, and update failure? | TBD | Open |
| OQ-13 | What coexistence, migration, compatibility, fallback, and rollback requirements apply relative to conventional SDR? | TBD | Open |
| OQ-14 | What AGPL-3.0, dependency-license, intellectual-property, and source-availability implications apply? | TBD | Open |
| OQ-15 | What legal, export-control, certification, equipment-authorization, safety, and compliance reviews are required? | TBD | Open |

### 17.2 Decision log

Add an entry to this table only after an identifiable review and approval decision has been made.

| Decision ID | Date | Decision | Rationale | Approver or review authority | Evidence or reference |
| --- | --- | --- | --- | --- | --- |
| TBD | TBD | TBD | TBD | TBD | TBD |

---

## 18. References and Cross-References

- [01 — MHRP System Specification](01_MHRP_System_Specification.md)
- [03 — MHRP Engineering Master Roadmap](03_MHRP_Engineering_Master_Roadmap.md)
- [04 — MHRP Theoretical Frameworks](04_MHRP_Theoretical_Frameworks.md)
- [05 — MHRP Sovereign Boot Image Instructions](05_MHRP_Sovereign_Boot_Image_Instructions.md)

External references, standards, legal sources, test methods, hardware references, and other authoritative materials are TBD and must be added only after source review.

---

## Appendix A. Requirement Traceability Matrix

This appendix is TBD.

Before this matrix is completed, the project must identify the authoritative requirements in `01_MHRP_System_Specification.md`, the relevant roadmap dependencies in `03_MHRP_Engineering_Master_Roadmap.md`, and the approval status of the requirements in Section 4.

| Requirement ID | Source document or decision | Architecture section | Validation evidence | Status |
| --- | --- | --- | --- | --- |
| TBD | TBD | TBD | TBD | TBD |

---

## Appendix B. Interface Sketches

This appendix is TBD.

Any future diagrams or interface sketches must be clearly marked as conceptual unless and until they are reviewed, approved, and supported by implementation evidence.

---

## Appendix C. Regulatory and Threat Matrices

This appendix is TBD.

Any future matrix must distinguish among:

- Assumptions.
- Jurisdiction-specific legal or regulatory requirements.
- Security threats.
- Safety risks.
- Required reviewers.
- Evidence needed before implementation or field evaluation.

No compliance conclusion may be inferred from the existence of this appendix.
