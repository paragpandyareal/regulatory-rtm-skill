# Document Type Extraction Guide

Different types of regulatory documents have different structures, conventions, and traps. This guide helps you extract requirements more effectively from each type.

## Primary Legislation (Acts of Parliament, Statutes)

**Typical structure:** Parts > Divisions > Sections > Subsections > Paragraphs

**Extraction tips:**
- Definitions are usually in Section 2 or a dedicated "Interpretation" Part at the start. Read these first because they change the meaning of words used throughout the Act
- Commencement provisions (usually Section 1 or 2) tell you when obligations take effect. Some sections may commence on different dates
- Schedules at the end often contain the most detailed operational requirements. Never skip them
- Penalty provisions are often in a separate Part. Extract each penalty and link it to the requirement it enforces
- "Subject to" clauses create a hierarchy between provisions. When Section A says "Subject to Section B", it means Section B overrides Section A where they conflict. Flag both and note the relationship
- "Despite" or "Notwithstanding" clauses do the opposite. They override other provisions. Flag these clearly
- Purpose and objects clauses (usually Section 3) aren't obligations themselves but they guide interpretation of everything else. Capture them with a note explaining this

## Subordinate Legislation (Regulations, Rules, Orders, Instruments)

**Typical structure:** Varies, but often Parts > Regulations/Rules > Sub-rules

**Extraction tips:**
- Always note which Act enables (authorises) the regulations. The enabling Act sets the boundaries of what the regulations can do
- Subordinate legislation can be amended or revoked independently of the parent Act
- Often more operationally detailed than the Act. Expect higher extraction density (more requirements per page)
- May reference the parent Act's definitions section. If a term isn't defined in the regulations, check the Act
- Some instruments have sunset clauses (automatic expiry dates). Flag these

## EU Directives vs EU Regulations

**Directives:**
- Must be transposed (converted) into national law by each Member State
- The obligation is to achieve the result, not necessarily to copy the text
- When extracting, flag each requirement with "Transposition required" in Implementation Notes
- Recitals at the start provide context but are not binding. However, courts use them to interpret the Articles, so capture any that narrow or expand the meaning of an Article

**Regulations:**
- Directly applicable in all Member States. No transposition needed
- Extract requirements the same way as national legislation
- "Delegated acts" and "implementing acts" are secondary instruments made under the Regulation. Flag references to these as needing separate review

**Common EU phrasing:**
- "Member States shall ensure..." means the government must implement something
- "The controller shall..." is a direct obligation on organisations
- "Without prejudice to..." means this provision doesn't override another one

## US Code of Federal Regulations (CFR)

**Structure:** Title > Chapter > Part > Subpart > Section

**Extraction tips:**
- Definitions are usually in Subpart A or the first section of each Part (e.g., Section 164.103 in HIPAA)
- The Federal Register preamble explains the agency's intent when finalising the rule. It is not binding but useful for INTERPRETED entries when the rule text is ambiguous
- Cross-references to the United States Code (USC) point to the enabling statute. Flag these for separate review
- "Shall" and "must" are both mandatory. "Will" is often mandatory too (not just future tense)
- "No person may..." means prohibition, not permission
- Appendices to Parts contain detailed requirements (forms, standards, methodologies). Don't skip them

## Australian National Electricity/Gas/Energy Retail Rules

**Structure:** Parts > Chapters > Rules > Clauses > Sub-clauses

**Extraction tips:**
- Definitions are in Chapter 10 (NER), Chapter 11 (NGR), or a separate definitions chapter
- Model Provisions have different legal status from Rules. Model Provisions are templates that jurisdictions may adopt, modify, or not adopt. Flag the distinction
- Amendment instruments reference specific rule numbers being changed. When extracting from an amendment, capture both the old text (as DELETED) and the new text (as NEW or AMENDED)
- Schedules contain detailed procedures (e.g., metering procedures, settlement calculations). These are some of the most operationally detailed sections
- Transitional provisions (often in a Part at the end) specify phased implementation. Extract each phase as a separate TIMELINE requirement

## ISO, IEC, and National Standards (AS/NZS, BS, ANSI)

**Extraction tips:**
- "Shall" is mandatory, "Should" is recommended, "May" is permitted, "Can" is capability. This is formally defined in ISO/IEC Directives Part 2 and is consistent across all ISO family standards
- Normative sections contain requirements. Informative sections (usually Annexes marked "Informative") do not contain requirements. Check the label on each Annex
- Normative references (usually Clause 2) list other standards that are incorporated by reference. Requirements in those referenced standards become indirect obligations. Flag each for separate review
- Terms and definitions (usually Clause 3) are binding within the standard. A defined term means exactly what the definition says, not what the word means in everyday language
- Notes within normative sections provide clarification but are not themselves requirements
- Figures and tables in normative sections can contain requirements (e.g., parameter limits, test criteria). Don't skip them

## Financial Services Regulations (APRA, ASIC, Basel, SOX)

**Extraction tips:**
- Distinguish between prudential standards (legally binding) and prudential practice guides (guidance, not binding). Both may be issued by the same regulator but have very different legal force
- Proportionality requirements mean obligations scale with entity size, complexity, or risk profile. Flag these and note the scaling criteria
- Reporting requirements often come with specific templates, forms, and due dates. The template itself is an obligation (you must use this specific format). Extract both the reporting obligation and the format requirement
- Capital and liquidity requirements involve formulas. Capture the formula verbatim and explain each variable in the Plain English Summary
- Board and governance obligations (e.g., board approval, risk committee oversight) are distinct from operational obligations. Tag these in the Governance business domain

## Privacy and Data Protection (GDPR, Privacy Act, CDR)

**Extraction tips:**
- Data subject rights (access, rectification, erasure, portability, objection) each create multiple obligations on controllers and processors. Extract each right AND each corresponding obligation separately
- Lawful basis requirements (consent, legitimate interest, legal obligation, etc.) are foundational. If the lawful basis isn't established, many other obligations don't apply. Flag this dependency
- Cross-border data transfer restrictions have their own compliance mechanisms (adequacy decisions, standard contractual clauses, binding corporate rules). Each mechanism has sub-requirements
- Breach notification typically has specific timelines (GDPR: 72 hours to authority, "without undue delay" to data subjects). Extract both the timeline and the notification content requirements
- Data Protection Impact Assessments (DPIAs) are triggered by specific conditions. Extract both the trigger conditions and the DPIA process requirements
- Processor obligations are distinct from controller obligations. Tag the Responsible Party correctly

## Workplace Health and Safety (WHS/OHS)

**Extraction tips:**
- SFAIRP (so far as is reasonably practicable) is the core standard. It means you must do everything reasonable to eliminate or minimise risk, considering the likelihood of the hazard, the degree of harm, what the person knows or ought to know, and the cost of controls. Extract SFAIRP obligations as MUST DO with the SFAIRP qualification noted
- Duty holder hierarchy matters: PCBU (Person Conducting a Business or Undertaking) has the primary duty, officers have a due diligence duty, workers have a duty to take reasonable care. Tag Responsible Party correctly
- Notifiable incidents must be reported AND the site must be preserved. These are two separate obligations with different timelines. Extract both
- The risk management hierarchy (eliminate > substitute > isolate > engineering controls > administrative controls > PPE) is itself a requirement in many jurisdictions
- Regulations and Codes of Practice sit under the Act. Codes of Practice are not strictly mandatory but following them is evidence of compliance with the Act

## Amendment and Rule Change Documents

**Extraction tips:**
- For "omit X, substitute Y" amendments: create a DELETED entry for the old provision (X) and a NEW entry for the substituted provision (Y)
- For "after paragraph (a) insert (aa)" amendments: capture the inserted text as NEW, and note where it fits in the existing structure
- For "in section Z, omit 'word', substitute 'other word'" amendments: create an AMENDED entry showing both the old and new text
- Always flag references to the existing instrument that the user hasn't provided. They need to read the amendment alongside the original to get the full picture
- Transitional provisions in amendments often say "these changes apply to X from [date] but existing Y continues under the old rules until [date]". Extract both the commencement and the transitional arrangement as separate requirements
- Some amendments renumber existing provisions. If you notice renumbering, note it so the user can update cross-references in their existing compliance matrix
