# ICIL — Scoring Methodology (v1)

**Project:** Influencer Integrity & Credibility Ledger (ICIL)  
**Document:** SCORING_METHODOLOGY_v1.md  
**Version:** v1.0  
**Status:** ACTIVE (Implements LOCKED v1)  
**Last Updated:** 2026-02-01  

---

## 1. Purpose

This document defines **how ICIL scores are derived, adjusted, and interpreted**.

It **implements** the rules defined in `LOCKED_STATE.md` and does not override or modify them.

The goal of the scoring system is to:
- Represent credibility-related signals in a **structured, neutral manner**
- Allow longitudinal tracking of credibility over time
- Prevent arbitrary, discretionary, or opaque manipulation

---

## 2. Core Scoring Philosophy

ICIL scoring is based on the following principles:

1. **Evidence-driven**  
   Scores reflect recorded evidence and its current validity status.

2. **Additive and subtractive over time**  
   Credibility is built, maintained, or degraded through observable actions.

3. **Non-binary**  
   Credibility is not “good” or “bad”; it exists on a spectrum.

4. **Non-predictive**  
   Scores do not forecast future behavior or outcomes.

5. **Non-endorsement**  
   A high score does not imply approval, recommendation, or certification.

---

## 3. Score Scale (LOCKED)

ICIL uses a **three-digit score range: 300–900**.

### 3.1 Interpretation Bands

- **300–499** → Low credibility  
- **500–699** → Developing credibility  
- **700–849** → High credibility  
- **850–900** → Exceptional credibility  

Scores outside this range are invalid.

---

## 4. Score Composition Model

An ICIL score is composed of **weighted evidence signals** evaluated over time.

### 4.1 Evidence Categories (Conceptual)

Evidence may fall into categories such as:
- Disclosure & transparency signals
- Compliance-related signals
- Dispute history
- Consistency of public claims
- Verification outcomes

> Note: Categories are **conceptual**, not exhaustive, and may evolve without changing the scoring philosophy.

---

### 4.2 Positive Signals

Positive signals generally include:
- Verified disclosures
- Consistent public claims supported by evidence
- Successful dispute resolutions in favor of the subject
- Long-term absence of adverse verified events

Positive signals **increase or stabilize** scores.

---

### 4.3 Negative Signals

Negative signals generally include:
- Invalidated or disputed evidence
- Proven inconsistencies between claims and evidence
- Repeated unresolved disputes
- Evidence expiration without renewal (where applicable)

Negative signals **decrease or dampen** scores.

---

## 5. Temporal Weighting (Time Sensitivity)

ICIL scoring is **time-aware**.

- Recent verified evidence has greater influence than outdated evidence
- Older evidence may decay in influence over time
- Expired evidence no longer contributes positively

This prevents both:
- Permanent punishment for old issues
- Permanent reward for stale credibility

---

## 6. Score Change Triggers (LOCKED)

Scores may change **only** due to:

1. Addition of verified evidence  
2. Expiration of existing evidence  
3. Resolution of verified disputes  

No other mechanism may alter a score.

---

## 7. What ICIL Explicitly Does NOT Do

To prevent misuse or misinterpretation, ICIL scoring:

- Does NOT rank entities against each other
- Does NOT predict trustworthiness or safety
- Does NOT assess intent or morality
- Does NOT replace due diligence
- Does NOT provide recommendations

Scores are **descriptive**, not prescriptive.

---

## 8. Manual Intervention & Overrides (LOCKED)

- Manual score overrides are prohibited
- Administrative roles cannot arbitrarily change scores
- All score-affecting actions must be traceable to evidence events

Any detected deviation constitutes a governance violation.

---

## 9. Transparency & Explainability

For each score, ICIL must be able to disclose:
- Current score value
- Score history over time
- Evidence states contributing to score movement
- Dispute outcomes affecting the score

However:
- Exact weighting formulas may remain undisclosed to prevent gaming
- Transparency is achieved through **traceability**, not full mathematical disclosure

---

## 10. Example (Illustrative, Non-Normative)

> An influencer with consistent verified disclosures over time maintains a high score.  
> A verified dispute temporarily reduces the score.  
> Upon resolution and evidence invalidation, the score partially recovers.  
> Long periods without new evidence result in gradual stabilization, not inflation.

This example is illustrative and does not define exact numerical behavior.

---

## 11. Relationship to Other Documents

This document operates alongside:
- `LOCKED_STATE.md`
- `EVIDENCE_SPECIFICATION_v1.md`
- `DISPUTE_PROCESS_v1.md`
- `GOVERNANCE_CHARTER_v1.md`

In case of conflict, `LOCKED_STATE.md` prevails.

---

## 12. Change Policy

- Clarifications may be added without changing version number
- Any rule change affecting scoring behavior requires a major version increment

---

**End of Document**
