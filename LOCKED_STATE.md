# ICIL v1 — LOCKED STATE DECLARATION

**Project:** Influencer Integrity & Credibility Ledger (ICIL)  
**Version:** v1.0  
**Status:** 🔒 LOCKED  
**Effective Date:** 2026-02-01  

---

## 1. Purpose of This Document

This document formally declares the **locked state** of ICIL v1.

Once locked:
- No breaking changes are permitted
- No scope expansion is allowed
- No reinterpretation of rules is allowed
- All future changes require a new major version (v2+)

ICIL v1 becomes a **reference-grade public registry specification**, not a prototype.

---

## 2. System Identity (LOCKED)

- **Name:** Influencer Integrity & Credibility Ledger  
- **Abbreviation:** ICIL  
- **Nature:** Neutral, informational public registry  
- **Function:** Recording and disclosing credibility-related signals  
- **Not a marketplace**  
- **Not an enforcement authority**  
- **Not a legal adjudication body**

ICIL does not certify, approve, recommend, or guarantee any entity.

---

## 3. Scope & Applicability (LOCKED)

ICIL applies to:
- Influencers
- Public digital creators
- Public-facing brands (where applicable)

ICIL is:
- Jurisdiction-agnostic
- Informational in nature
- Independent of platforms, agencies, or marketplaces

---

## 4. Scoring System (LOCKED)

### 4.1 Score Range
- **300 – 900** (three-digit scale)

### 4.2 Score Interpretation
- **300–499:** Low credibility
- **500–699:** Developing credibility
- **700–849:** High credibility
- **850–900:** Exceptional credibility

### 4.3 Scoring Principles
- Scores are informational only
- Scores are evidence-derived
- Scores do not predict outcomes
- Scores do not imply endorsement

### 4.4 Score Mutability
Scores may change only due to:
- Addition of verified evidence
- Expiration of evidence
- Resolution of verified disputes

Manual or discretionary score overrides are prohibited.

---

## 5. Evidence Model (LOCKED)

### 5.1 Evidence Structure
Each evidence record includes:
- Structured metadata
- Cryptographic hash
- Timestamp
- Submitter identity (role-based)

### 5.2 Evidence Storage Policy
- ICIL does **not** store raw evidence
- Only hashes and metadata are retained

### 5.3 Evidence States
- Submitted  
- Verified  
- Challenged  
- Disputed  
- Invalidated  
- Expired  

### 5.4 Immutability
- Evidence records are append-only
- Evidence cannot be modified once recorded
- Invalid evidence is marked, not deleted

### 5.5 Reproducibility
- Identical inputs must produce identical hashes

---

## 6. Dispute Resolution (LOCKED)

### 6.1 Eligibility
- Only the subject entity or authorized representatives may raise disputes

### 6.2 Dispute Scope
Disputes may address:
- Evidence authenticity
- Evidence relevance
- Procedural correctness

### 6.3 Dispute Outcomes
- Upheld
- Partially upheld
- Rejected
- Evidence invalidated

### 6.4 Auditability
- Disputes append outcomes
- Historical records are preserved
- No retroactive rewriting is permitted

---

## 7. Governance Model (LOCKED)

### 7.1 Governance Structure
- ICIL is overseen by an independent governing committee

### 7.2 Founder Limitations
- The founder has no unilateral control
- No scoring override authority
- No special access privileges

### 7.3 Conflict of Interest
- Conflicts must be disclosed
- Governance decisions must be auditable

### 7.4 Transparency
- Governance roles are publicly documented
- Governance changes are logged

---

## 8. Data & Privacy (LOCKED)

- ICIL stores no sensitive personal data
- No private contact details are publicly exposed
- Public data is limited to:
  - Entity identifier
  - Score and score history
  - Evidence hashes
  - Status metadata

Principles aligned with global data protection standards are observed.

---

## 9. API & Public Access (LOCKED)

- Public APIs are **read-only**
- No public write access is permitted
- Endpoints are versioned (`/api/v1`)
- Responses are non-interpretive (raw data only)
- Rate limiting is enforced

---

## 10. Public Language & Claims (LOCKED)

### 10.1 Prohibited Language
ICIL must not use:
- “Verified safe”
- “Trusted by ICIL”
- “Approved influencers”
- “Guaranteed credibility”

### 10.2 Approved Language
ICIL may use:
- “Recorded”
- “Assessed”
- “Documented”
- “Disclosed”

All language must remain neutral and factual.

---

## 11. Change Control Policy (LOCKED)

- ICIL v1 is immutable
- Any change requires:
  - Major version increment
  - Public documentation
  - Rationale and change log

No silent updates are permitted.

---

## 12. Lock Declaration

ICIL v1 is hereby declared **LOCKED**.

This version represents the authoritative baseline for:
- Public reference
- Audits
- Integrations
- Long-term trust evaluation

Future changes, if any, will occur only in subsequent major versions.

---

**End of Document**
