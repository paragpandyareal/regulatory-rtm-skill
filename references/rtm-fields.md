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

**Generic starter domains (use these as a starting point, then add industry-specific ones as needed):**
- **Operations** - Day-to-day business operations and processes
- **Finance** - Financial reporting, budgeting, treasury, prudential requirements
- **Legal** - Contractual obligations, dispute resolution, litigation
- **Compliance** - Compliance reporting, monitoring, audit, regulatory relationships
- **IT / Technology** - Systems, cybersecurity, data platforms, infrastructure
- **HR / People** - Training, qualifications, personnel requirements, workplace culture
- **Customer** - Customer service, complaints, hardship, customer-facing communications
- **Supply Chain** - Procurement, vendor management, third-party risk
- **Risk Management** - Enterprise risk, operational risk, risk appetite
- **Governance** - Board obligations, committee oversight, delegation authorities, internal controls
- **Data / Privacy** - Data handling, privacy, data exchange, records management
- **Safety / Environment** - Workplace health and safety, environmental obligations, sustainability
- **Communications** - Public disclosures, market announcements, stakeholder engagement
- **Procurement** - Acquisition, contracting, tender processes

**Energy sector example domains:** Billing, Metering, Market Operations, Settlement, Network Operations, Connection Services, Retail Operations, Generation, Transmission, Distribution

**Financial services example domains:** Lending, Insurance, Wealth Management, Trading, Treasury, Prudential, Conduct, Anti-Money Laundering, Credit Risk, Market Risk

**Healthcare example domains:** Clinical Governance, Patient Safety, Infection Control, Medicines Management, Medical Devices, Health Records, Clinical Trials, Workforce Registration

**Construction example domains:** Building Compliance, Site Safety, Environmental Management, Quality Assurance, Contract Administration, Planning Approvals, Heritage, Accessibility

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

## 12. Responsible Party

Who within the organisation (or which type of organisation) is responsible for compliance. If the regulation specifies this, use that. If not, make a reasonable inference and mark it as DERIVED.

**Examples:**
- `Registered Participants` (energy market term)
- `Data Controller` (GDPR term)
- `PCBU - Person Conducting a Business or Undertaking` (WHS term)
- `Chief Information Security Officer`
- `Board of Directors`
- `All staff`
- `Third-party processors`
- `To be confirmed` (if you genuinely cannot determine this)

A requirement can have multiple responsible parties. List the primary one first.

---

## 13. Dependencies

Other requirements that this one depends on or is linked to. This is about sequencing: what needs to happen before this requirement can be met?

**Examples:**
- `Depends on REQ-003 (system must be built before data can be submitted)`
- `Depends on REQ-015 (policy must be approved before training can be delivered)`
- `No dependencies - standalone requirement`
- `Blocked by: organisational decision on which vendor to use`

---

## 14. Change Type

For amendments and rule changes, what kind of change this represents. For new standalone regulations, everything is NEW.

| Type | Description |
|---|---|
| **NEW** | Brand new requirement that did not exist before |
| **AMENDED** | Modification of an existing requirement. Note both old and new text |
| **DELETED** | Requirement being removed. Still include it in the RTM so there is a record |
| **UNCHANGED** | Existing requirement not affected by this change. Include for completeness if analysing an amendment alongside the existing instrument |

---

## 15. Implementation Notes

Practical considerations for implementing this requirement. This is where you add context that helps the business team understand what they actually need to do.

**Examples:**
- `Requires changes to the billing system to calculate new tariff rates`
- `May need legal advice on whether existing contracts satisfy this requirement`
- `Training program needs to be developed - no off-the-shelf solution likely to cover this`
- `This is a new reporting obligation - check if existing data collection supports the required fields`
- `Cross-reference with existing privacy policy - may already be partially compliant`

---

## 16. Verification Method

How compliance with this requirement would be verified. This is useful for audit preparation and compliance monitoring program design.

| Method | Description | Example |
|---|---|---|
| **INSPECTION** | Review of documents, records, or artefacts | Checking that a policy exists and is signed |
| **TESTING** | Active testing of systems, processes, or controls | Running a penetration test, testing a backup restore |
| **DEMONSTRATION** | Showing that a process works in practice | Walking through the complaint handling process |
| **ANALYSIS** | Analytical assessment of data or reports | Reviewing incident statistics against benchmarks |
| **INTERVIEW** | Asking staff about their knowledge or practices | Checking that staff know the breach notification process |

A requirement may need multiple verification methods.

---

## 17. Risk if Non-Compliant

What happens if this requirement is not met. Be specific where the regulation specifies consequences.

**Examples:**
- `Civil penalty up to $500,000 per contravention`
- `Licence condition - breach may trigger regulatory investigation`
- `Customer complaint to ombudsman - potential compensation order`
- `Safety risk - potential for serious injury or death`
- `Regulatory direction to remediate within specified timeframe`
- `Reputational risk - public reporting of non-compliance`
- `No specific penalty stated but general enforcement powers apply under Section 45 of the Act`

---

## Advanced Fields

These fields are valuable for mature compliance programs doing detailed gap analysis, audit preparation, or framework mapping. For a quick first-pass analysis, you can skip these and add them later.

### 18. Control Reference

Mapping to existing control frameworks the organisation may already have in place.

**Examples:**
- `ISO 27001 A.8.1` (information asset inventory)
- `NIST CSF PR.AC-1` (identity management)
- `CIS Control 1.1` (enterprise asset inventory)
- `SOC 2 CC6.1` (logical access controls)

Useful for gap analysis: if a new regulation maps to an existing control, the organisation may already be partially compliant.

### 19. Evidence Required

What documentation or artefact would demonstrate compliance if an auditor asked.

**Examples:**
- `Signed and dated policy document, reviewed within last 12 months`
- `System logs showing encryption at rest enabled for all customer data stores`
- `Training completion records for all staff, dated within last 12 months`
- `Board minutes showing annual risk appetite review`
- `Incident response test report with findings and remediation actions`

### 20. Review Frequency

How often compliance with this requirement needs to be reassessed.

**Values:** `Continuous` (real-time monitoring), `Monthly`, `Quarterly`, `Semi-annual`, `Annual`, `Per-event` (triggered by a specific event like a breach or change), `Ad-hoc`

### 21. Applicability Scope

Which specific entities, products, services, or geographies this requirement applies to. More granular than Business Domain.

**Examples:**
- `All retail electricity customers in Victoria`
- `Organisations processing personal data of EU residents`
- `Category 1 licensees with annual revenue over $50M`
- `All cloud-hosted production systems`

### 22. Regulatory Authority

Who enforces this requirement. May be different from the body that issued the document.

**Examples:**
- `Australian Energy Regulator (AER)` - enforces National Energy Retail Law
- `Information Commissioner's Office (ICO)` - enforces UK GDPR
- `Securities and Exchange Commission (SEC)` - enforces SOX
- `State workplace health and safety regulator` - varies by jurisdiction

### 23. Penalty Details

Specific penalty amounts, ranges, or penalty unit references for non-compliance.

**Examples:**
- `Civil penalty up to 300 penalty units ($93,900 per unit as at 2025-26)`
- `Administrative fine up to EUR 20 million or 4% of global annual turnover, whichever is higher (GDPR Art. 83(5))`
- `Infringement notice up to $50,000 per contravention`
- `Licence condition - breach may result in licence suspension or revocation`
- `No specific penalty stated - enforced through general compliance powers`

### 24. Transition Period

For phased implementations, which phase this requirement falls into.

**Examples:**
- `Phase 1: effective 1 July 2026`
- `Phase 2: effective 1 January 2027 (systems readiness)`
- `Grandfathered: existing arrangements continue until 1 July 2028`
- `Immediate: effective on commencement`

### 25. Supersedes

Which previous requirement(s) this replaces or amends.

**Examples:**
- `Replaces REQ-045 from RTM v1.0 (old Rule 7.3)`
- `Amends the existing requirement under Section 12(1) of the 2019 Act`
- `New requirement - no predecessor`

### 26. Related Requirements

Cross-references to other requirements within the same RTM. Different from Dependencies (which is about sequencing). Related Requirements are about subject matter connections.

**Examples:**
- `Related to REQ-012 (same obligation but for different customer type)`
- `See also REQ-034 (reporting obligation that depends on this data collection requirement)`
- `Contradicts REQ-078 - needs human review to determine which takes priority`

### 27. Confidence Score

How confident the extraction is, with reasoning. Pairs with Source Type.

**Values:** `HIGH`, `MEDIUM`, `LOW`

**Examples:**
- `HIGH - Clear mandatory language ("must"), specific timeframe, unambiguous scope`
- `MEDIUM - Obligation is clear but scope depends on interpretation of "material change"`
- `LOW - Derived from a general purpose clause; may not create a standalone obligation. Flagged for legal review`

Use HIGH for clear VERBATIM requirements, MEDIUM for requirements where some interpretation was needed, LOW for DERIVED/ASSUMED requirements where you are not sure the obligation actually exists.

---

## Handling Non-Text Content

Regulatory documents often contain tables, formulas, flowcharts, and diagrams that contain obligations. Don't skip these.

**Tables in regulations:**
Treat each row of a compliance table as a potential requirement. Fee schedules, penalty tables, reporting matrices, and classification tables all contain obligations. Capture the table title and the specific row/column as the Source Reference (e.g., "Schedule 2, Table 3, Row 5").

**Formulas:**
When a regulation includes a calculation formula (pricing formulas, penalty calculations, capital adequacy ratios), capture the formula verbatim. In the Plain English Summary, explain what each variable represents and what the formula calculates.

**Flowcharts and decision trees:**
Extract each decision point and each outcome as separate requirements. The decision conditions become CONDITIONAL requirements. Note that flowcharts in PDFs are often embedded as images and may not be machine-readable. If you cannot read a flowchart, flag it with "Visual flowchart on page X - manual review required".

**Maps and diagrams:**
If a regulation uses a map to define geographic boundaries (e.g., network service areas) or a diagram to define system architectures, note the existence of the visual element and flag it for manual review. Describe what the map/diagram appears to show based on surrounding text.
