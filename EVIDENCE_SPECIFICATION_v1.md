# ICIL — Evidence Specification (v1)

**Project:** Influencer Integrity & Credibility Ledger (ICIL)  
**Document:** EVIDENCE_SPECIFICATION_v1.md  
**Version:** 1.0  
**Status:** ACTIVE — Implements LOCKED v1  
**Last Updated:** 2026-02-01  

---

## 1. Purpose

This document defines the **canonical structure, submission rules, verification methods,
hashing requirements, lifecycle states, and audit guarantees** for all evidence recorded
within the Influencer Integrity & Credibility Ledger (ICIL).

The intent of this specification is to ensure that ICIL evidence is:

- **Auditable** by independent parties  
- **Tamper-evident** through deterministic hashing  
- **Reproducible** without reliance on ICIL infrastructure  
- **Non-repudiable** once submitted  
- **Independent of raw or sensitive data storage**  

This document **implements and enforces** the constraints defined in `LOCKED_STATE.md`.
In the event of conflict, `LOCKED_STATE.md` SHALL prevail.

---

## 2. Foundational Principles

All ICIL evidence **MUST** adhere to the following principles:

1. **Structured**  
   Evidence MUST follow a predefined schema. Free-form submissions are not permitted.

2. **Hash-addressable**  
   Each evidence item is identified by a deterministic cryptographic fingerprint.

3. **Append-only**  
   Evidence, once submitted, can never be altered or deleted.

4. **Verifiable**  
   Evidence MUST support independent verification without ICIL acting as an authority.

5. **Minimal Disclosure**  
   ICIL SHALL NOT store raw documents, personal data, or sensitive content.

These principles are **non-negotiable** and apply to all evidence types, roles, and entities.

---

## 3. Evidence Lifecycle States (LOCKED)

Each evidence item SHALL exist in **exactly one** of the following states at any time:

- `SUBMITTED` — Evidence accepted but not yet verified  
- `VERIFIED` — Evidence independently verified  
- `CHALLENGED` — Evidence formally questioned  
- `DISPUTED` — Evidence under active dispute resolution  
- `INVALIDATED` — Evidence proven false or unreliable  
- `EXPIRED` — Evidence no longer contributes to scoring  

All state transitions are:

- Logged immutably  
- Append-only  
- Irreversible  

---

## 4. Evidence Envelope (Canonical Structure)

Every evidence submission **MUST** conform to the canonical envelope defined below.
Submissions not conforming to this structure SHALL be rejected.

### 4.1 Required Fields

```json
{
  "evidence_id": "uuid-v7",
  "entity_id": "icil:entity:<identifier>",
  "evidence_type": "string",
  "evidence_category": "string",
  "claim_summary": "string",
  "evidence_hash": "sha256",
  "hash_algorithm": "SHA-256",
  "submitted_by": "role",
  "submission_timestamp": "ISO-8601",
  "evidence_timestamp": "ISO-8601",
  "verification_method": "string",
  "current_state": "ENUM",
  "version": "1.0"
}
```

All fields are mandatory unless explicitly stated otherwise by a future version.

---

## 5. Evidence Hashing & Reproducibility

### 5.1 Hash Input Rules

The `evidence_hash` MUST be derived from:

- Normalized evidence content
- Deterministic field ordering
- Canonical UTF-8 encoding

The hash input MUST NOT include ICIL-generated metadata
(e.g., `evidence_id`, `submission_timestamp`).

**Conceptual example:**

```
hash = SHA256(
  normalize(evidence_content)
  + evidence_timestamp
  + verification_method
)
```

### 5.2 Reproducibility Guarantee

Given:

- Identical underlying evidence
- Identical normalization rules

The resulting hash MUST be identical across systems.

Non-reproducible hashes SHALL be rejected by ICIL.

---

## 6. Evidence Types (Extensible)

Evidence types define **what is being proven**, not how it is scored.

**Non-exhaustive examples:**

- Public disclosure records
- Platform verification confirmations
- Contractual or legal attestations
- Dispute outcomes
- Public corrections or retractions

New evidence types MAY be introduced without breaking v1,
provided they comply with this specification.

---

## 7. Verification Requirements

Each evidence item MUST declare a verification method, such as:

- Cryptographic signature validation
- Platform-issued confirmation
- Public registry verification
- Third-party attestation

Evidence without a verifiable method:

- MAY be submitted
- CANNOT reach the `VERIFIED` state

Verification does not imply endorsement, only validity.

---

## 8. Evidence Submission Roles

Evidence MAY be submitted by:

- Subject entity (self-disclosure)
- Authorized representative
- Independent third party
- ICIL governance authority (procedural evidence only)

Submission role influences verification rigor,
but NEVER alters evidence structure or lifecycle rules.

---

## 9. State Transition Rules

Only the following state transitions are permitted:

```
SUBMITTED   → VERIFIED
SUBMITTED   → CHALLENGED
VERIFIED    → CHALLENGED
CHALLENGED  → DISPUTED
DISPUTED    → VERIFIED
DISPUTED    → INVALIDATED
VERIFIED    → EXPIRED
```

Any transition outside this graph is explicitly prohibited.

---

## 10. Immutability & Corrections

- Evidence content is immutable after submission
- Errors or corrections require new evidence submissions
- Superseding evidence MUST reference the prior `evidence_id`
- Historical records are preserved permanently
- ICIL never overwrites history

---

## 11. Evidence Expiration

Certain evidence types MAY define expiration conditions.

Upon expiration:

- State becomes `EXPIRED`
- Score contribution becomes zero
- Evidence remains publicly auditable
- Expiration does not imply falsity or invalidation

---

## 12. Public Visibility Rules

The following fields SHALL be publicly visible:

- Evidence ID
- Evidence type and category
- Hash and hash algorithm
- Current lifecycle state
- Timestamps

Raw evidence content is never stored or exposed by ICIL.

---

## 13. Auditability & Traceability

For every evidence item, ICIL MUST expose:

- Complete state transition history
- Verification metadata
- Dispute references
- Supersession links

This enables independent third-party audits
without reliance on ICIL as a trusted intermediary.

---

## 14. Security & Abuse Prevention

ICIL MUST implement:

- Rate limiting for evidence submissions
- Duplicate and spam detection
- Strict schema validation
- Immutable logging of all state changes

Abuse resistance is a core system requirement, not optional.

---

## 15. Relationship to Other ICIL Documents

This specification operates in conjunction with:

- `LOCKED_STATE.md`
- `SCORING_METHODOLOGY_v1.md`
- `DISPUTE_PROCESS_v1.md`
- `GOVERNANCE_CHARTER_v1.md`

In all conflicts, `LOCKED_STATE.md` takes precedence.

---

## 16. Change & Versioning Policy

- Clarifications MAY be added without a version bump
- Structural or semantic changes REQUIRE a major version increment
- Once locked, v1 rules SHALL remain permanently auditable

---

*Version: 1.0*  
*Last Updated: 2026-02-01*

