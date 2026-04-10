# RTM Fields Reference

Detailed descriptions and examples for every field in the Regulatory Requirements Traceability Matrix. Use this as a reference when populating the RTM.

## Table of Contents

1. [Requirement ID](#1-requirement-id)
2. [Source Reference](#2-source-reference)
3. [Source Document](#3-source-document)
4. [Verbatim Text](#4-verbatim-text)
5. [Plain English Summary](#5-plain-english-summary)
6. [Source Type](#6-source-type)
7. [Business Domain](#7-business-domain)
8. [Obligation Type](#8-obligation-type)
9. [Priority](#9-priority)
10. [Compliance Status](#10-compliance-status)
11. [Effective Date](#11-effective-date)
12. [Responsible Party](#12-responsible-party)
13. [Dependencies](#13-dependencies)
14. [Change Type](#14-change-type)
15. [Implementation Notes](#15-implementation-notes)
16. [Verification Method](#16-verification-method)
17. [Risk if Non-Compliant](#17-risk-if-non-compliant)

---

## 1. Requirement ID

A unique identifier for each requirement in the matrix. Use a consistent format throughout.

**Format:** `REQ-001`, `REQ-002`, etc.

For large documents with clear sections, you can prefix with the section letter or number:
- `A-REQ-001` (Section A, requirement 1)
- `S3-REQ-001` (Schedule 3, requirement 1)

Never reuse an ID, even if a requirement is deleted during analysis.

---

## 2. Source Reference

The exact location within the source document where this requirement comes from. This must be specific enough that someone can find the exact clause in the original document.

**Good examples:**
- `Section 14(2)(b)`
- `Schedule 1, Rule 3.2(a)(i)`
- `Clause 7.1.1`
- `Part 3, Division 2, Section 45`
- `Appendix A, Table 3, Row 5`
- `Definition of "small customer" (Section 2)`

**Bad examples:**
- `Section 14` (too vague if Section 14 has multiple subsections)
- `Page 23` (page numbers change between document versions)
- `Near the beginning` (not a reference)

For DERIVED or ASSUMED requirements, reference the clause that the derivation or assumption is based on.

---

## 3. Source Document

The full name of the regulatory document, including version, date, or reference number if available.

**Examples:**
- `National Electricity Rules Version 215, effective 1 July 2026`
- `AEMC Final Determination - Metering Rule Change, 15 March 2026`
- `Energy Retail Code of Practice v4.0, 1 January 2026`
- `Consumer Data Right (Energy Sector) Rules 2025`

---

## 4. Verbatim Text

The exact text from the regulatory document, copied word for word. This is the most important field for maintaining trust and auditability.

**Rules:**
- Copy the exact text, including any unusual capitalisation, punctuation, or numbering
- If the regulation has a typo, copy the typo (you can add a note flagging it)
- Include enough context to make the clause understandable on its own
- If the clause is very long (more than ~200 words), include the full text but bold or highlight the key obligation words (shall, must, etc.)
- For DERIVED or ASSUMED requirements, this field should say "N/A - Derived from [source reference]" or "N/A - Assumed based on [reasoning]"

---

## 5. Plain English Summary

What this requirement actually means, written in simple language that someone without regulatory expertise could understand. This is where you translate legal/regulatory language into everyday terms.

**Rules:**
- No jargon. If a technical term is unavoidable, explain it in brackets
- Write in active voice ("You must..." not "It is required that...")
- Be specific about WHO needs to do WHAT by WHEN
- Don't add meaning that isn't in the original text
- If the requirement is genuinely complex, break it into bullet points

**Good example:**
Verbatim: "A Registered Participant must, within 5 business days of becoming aware of a material change in circumstances, notify AEMO in writing."
Plain English: "If something significant changes in your business (like ownership, systems, or operations), you need to tell AEMO about it in writing within 5 business days of finding out."

**Bad example:**
Plain English: "You should probably let AEMO know if things change." (too vague, loses the timeframe, loses the "material" qualifier)

---

## 6. Source Type

How this requirement was identified. This is critical for transparency.

| Type | Description | Confidence Level |
|---|---|---|
| **VERBATIM** | Exact text from the document. The requirement is explicitly stated | Highest |
| **DERIVED** | Logically follows from a verbatim requirement. Not stated word-for-word but clearly implied | High |
| **INTERPRETED** | The regulation is ambiguous and this is one reasonable interpretation. Other interpretations may be valid | Medium |
| **ASSUMED** | Not in the document but typically needed for compliance. Based on experience or common practice | Lower - requires human review |

Always err on the side of marking something as DERIVED or INTERPRETED rather than VERBATIM if you've changed any wording.

---

## 7. Business Domain

Which part of the business this requirement applies to. Use these standard categories and add domain-specific ones as needed:

**Standard domains:**
- **Billing** - Customer billing, invoicing, payment processing
- **Metering** - Meter data, meter installation, meter reading
- **Customer Communications** - Notices, disclosures, customer-facing information
- **IT Systems** - Technology platforms, data systems, cybersecurity
- **Market Operations** - Market participation, bidding, dispatch
- **Settlement** - Financial settlement, reconciliation
- **Registration** - Participant registration, licensing
- **Compliance** - Compliance reporting, monitoring, audit
- **Legal** - Contractual obligations, dispute resolution
- **Finance** - Financial reporting, prudential requirements
- **Network Operations** - Grid operations, network management
- **Data Management** - Data handling, privacy, data exchange
- **Human Resources** - Training, qualifications, personnel requirements
- **Governance** - Board obligations, risk management, internal controls
- **Customer Service** - Complaints, hardship, life support
- **Procurement** - Acquisition, contracting, vendor management

A requirement can belong to multiple domains. List the primary domain first, then secondary ones.

---

## 8. Obligation Type

What kind of obligation this requirement creates.

| Type | Trigger Words | Example |
|---|---|---|
| **MUST DO** | shall, must, is required to, will | "The retailer must issue a bill within 20 business days" |
| **MUST NOT DO** | shall not, must not, is prohibited from | "A distributor must not disconnect a life support customer" |
| **MAY DO** | may, can, is permitted to | "A retailer may offer flexible payment plans" |
| **CONDITIONAL** | if, where, when, provided that, unless | "If the customer requests, the retailer must provide usage data" |
| **REPORTING** | report, notify, inform, disclose, submit | "Participants must submit quarterly compliance reports" |
| **RECORD KEEPING** | maintain records, keep records, retain, document | "Records must be retained for a minimum of 7 years" |
| **TIMELINE** | by [date], within [period], no later than | "Implementation must be complete by 1 July 2026" |

Note: A requirement can have multiple types. For example, "The retailer must, within 10 business days, notify the customer in writing" is both MUST DO and TIMELINE.

---

## 9. Priority

Assessment of how critical this requirement is, based on obligation type and consequences.

| Priority | Criteria |
|---|---|
| **CRITICAL** | Non-compliance could result in penalties, licence revocation, safety incidents, or significant regulatory action. Typically MUST DO or MUST NOT DO requirements with explicit enforcement provisions |
| **HIGH** | Mandatory requirement with significant business or customer impact. Non-compliance would likely be noticed by the regulator |
| **MEDIUM** | Important requirement but with less immediate or severe consequences. May include CONDITIONAL or REPORTING requirements |
| **LOW** | Permissive requirements (MAY DO), minor record keeping, or requirements with minimal practical impact |

When in doubt, err on the side of higher priority. It's safer to over-prioritise than to under-prioritise a regulatory requirement.

---

## 10. Compliance Status

Current compliance state. For a new analysis where no assessment has been done, default to NOT ASSESSED.

| Status | Meaning |
|---|---|
| **NOT ASSESSED** | No compliance assessment has been performed yet |
| **COMPLIANT** | Fully meeting this requirement |
| **PARTIALLY COMPLIANT** | Meeting some aspects but gaps remain |
| **NON-COMPLIANT** | Not currently meeting this requirement |
| **NOT APPLICABLE** | This requirement does not apply to the organisation (with justification) |
| **IN PROGRESS** | Actively working on achieving compliance |

---

## 11. Effective Date

When this requirement comes into force. Extract from the document if specified.

**Formats:**
- Specific date: `1 July 2026`
- Relative: `6 months after commencement`
- Conditional: `Upon ministerial approval`
- Already in force: `Currently in effect`
- Not specified: `Not specified in document`

---

## 12-17. Remaining Fields

See the main SKILL.md for descriptions of Responsible Party, Dependencies, Change Type, Implementation Notes, Verification Method, and Risk if Non-Compliant. These follow the same principle of transparency and should only be populated with information that can be traced back to the source document or clearly flagged as derived/assumed.
