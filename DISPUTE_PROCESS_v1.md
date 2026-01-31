# ICIL — Dispute Process (v1)

**Project:** Influencer Integrity & Credibility Ledger (ICIL)  
**Document:** DISPUTE_PROCESS_v1.md  
**Version:** v1.0  
**Status:** ACTIVE (Implements LOCKED v1)  
**Last Updated:** 2026-02-01  

---

## 1. Purpose

This document defines the **formal process** by which evidence recorded in ICIL may be challenged, reviewed, and resolved.

The dispute system exists to:
- Protect subjects from incorrect or misapplied evidence
- Preserve auditability and historical integrity
- Prevent retroactive rewriting of records
- Ensure procedural fairness without discretionary judgment

This process **implements** the constraints defined in `LOCKED_STATE.md`.

---

## 2. Core Principles

All disputes within ICIL operate under the following principles:

1. **Procedural, not subjective**  
   Disputes assess evidence validity and process, not intent or character.

2. **Append-only outcomes**  
   Disputes add records; they never erase history.

3. **Role-bound authority**  
   Only authorized roles may initiate or resolve disputes.

4. **Evidence-centric resolution**  
   Outcomes are based solely on verifiable evidence and process compliance.

---

## 3. Eligibility to Dispute (LOCKED)

A dispute may be initiated only by:
- The subject entity of the evidence
- An authorized legal or contractual representative of the subject

Third parties may not initiate disputes on behalf of a subject.

---

## 4. Disputable Scope (LOCKED)

Disputes are limited strictly to:

- **Evidence authenticity**  
  (Was the evidence genuine and correctly represented?)

- **Evidence relevance**  
  (Does the evidence apply to the stated claim and entity?)

- **Procedural correctness**  
  (Was ICIL’s evidence handling compliant with its own rules?)

Disputes may NOT address:
- Opinions
- Moral judgments
- Score dissatisfaction without evidence error
- Future or speculative harm

---

## 5. Dispute Lifecycle States (LOCKED)

Each dispute exists in exactly one state:

- `FILED`
- `UNDER_REVIEW`
- `RESOLVED`
- `CLOSED`

State transitions are logged and immutable.

---

## 6. Dispute Filing Requirements

A valid dispute submission MUST include:

- Reference to the disputed `evidence_id`
- Dispute scope classification
- Supporting counter-evidence or procedural claim
- Declaration of accuracy by the filer
- Filing timestamp

Incomplete or malformed disputes are rejected.

---

## 7. Review Authority

Disputes are reviewed by:
- The ICIL governance review panel
- Or a designated procedural subcommittee

Reviewers must:
- Declare conflicts of interest
- Recuse themselves where conflicts exist

No single individual may unilaterally resolve a dispute.

---

## 8. Review Process

### 8.1 Review Focus

Reviewers assess:
- Evidence reproducibility
- Verification method validity
- Procedural adherence
- Submitted counter-evidence

Reviewers MUST NOT assess:
- Popularity
- Commercial impact
- Reputational harm
- Subjective fairness

---

### 8.2 Timeframes

- Dispute acknowledgment: within a defined operational window
- Review duration: reasonable and documented
- Extensions: permitted only with recorded justification

ICIL does not guarantee expedited resolution.

---

## 9. Dispute Outcomes (LOCKED)

A dispute may result in one of the following outcomes:

- **Upheld**  
  → Evidence is invalidated or corrected via superseding evidence

- **Partially upheld**  
  → Specific claims or components are invalidated

- **Rejected**  
  → Evidence remains valid and unchanged

- **Evidence invalidated**  
  → Evidence state becomes `INVALIDATED`

Outcomes are final for the evidence instance.

---

## 10. Effects on Evidence & Score

- Dispute outcomes modify **evidence state only**
- Score changes occur automatically via the scoring engine
- No direct score manipulation occurs during disputes

Historical scores remain traceable to their context.

---

## 11. Transparency & Public Record

Publicly visible dispute metadata includes:
- Dispute ID
- Related evidence ID
- Dispute scope
- Final outcome
- Resolution timestamp

Confidential materials are not exposed.

---

## 12. Abuse Prevention

ICIL MAY:
- Rate-limit dispute filings
- Reject repetitive or abusive filings
- Flag bad-faith patterns for governance review

Abuse mitigation actions are logged and reviewable.

---

## 13. No Retroactive Rewriting (LOCKED)

- Evidence history is preserved permanently
- Disputes append outcomes
- Deleted or hidden history is prohibited

This ensures long-term auditability.

---

## 14. Relationship to Other Documents

This document operates alongside:
- `LOCKED_STATE.md`
- `SCORING_METHODOLOGY_v1.md`
- `EVIDENCE_SPECIFICATION_v1.md`
- `GOVERNANCE_CHARTER_v1.md`

In case of conflict, `LOCKED_STATE.md` prevails.

---

## 15. Change Policy

- Clarifications may be added without version change
- Procedural changes require a major version increment

---

**END OF DOCUMENT**
