---
name: regulatory-rtm
description: Create comprehensive Regulatory Requirements Traceability Matrices (RTM) from regulatory documents, legislation, rule changes, policies, or compliance standards. Use this skill whenever the user asks to analyse a regulation, extract requirements from a regulatory document, create a traceability matrix, map regulatory obligations, build a compliance matrix, or trace requirements from any official document like legislation, rules, standards, or policy papers. Also trigger when the user uploads a PDF or document and asks what obligations or requirements it contains, what they need to comply with, or wants the regulatory text broken down into plain English. This skill handles the analysis and structuring only, and is output-format agnostic. The user can request output as a Confluence page, Word document, Excel spreadsheet, or any other format.
---

# Regulatory Requirements Traceability Matrix (RTM) Skill

This skill analyses regulatory documents (legislation, rule changes, standards, policies) and produces a comprehensive Requirements Traceability Matrix that maps every obligation to its source, explains it in plain English, categorises it by business domain, and clearly flags what is verbatim from the source vs what has been derived or assumed.

## When to Use This Skill

Use this whenever the user provides a regulatory document and wants to understand what it requires. This includes new regulations, rule changes, amendments, compliance standards, policy papers, or any official document that creates obligations.

## Core Principle: Honesty About Sources

The most important principle in this skill is **never making things up and always being transparent about where information came from**. Every single entry in the RTM must be clearly marked as one of the following:

| Source Type | What It Means | When to Use |
|---|---|---|
| **VERBATIM** | Exact text copied directly from the regulatory document, word for word | When quoting the actual clause, rule, or requirement text |
| **DERIVED** | A requirement that is not stated word-for-word but is clearly implied or logically follows from the verbatim text | When the regulation says "participants must submit data monthly" and you derive that they need a data submission system |
| **ASSUMED** | Something that would typically be needed to comply but is not explicitly stated in the document | When you flag that training would likely be needed even though the regulation doesn't mention it. Always explain why this assumption was made |
| **INTERPRETED** | Where ambiguous regulatory language has been interpreted in a specific way | When a clause uses vague terms like "reasonable" or "appropriate" and you've interpreted what that means in practice |

If the user hasn't provided enough information to fill a field, leave it as "To be confirmed" rather than guessing.

## RTM Structure

Every requirement extracted from a regulatory document should be captured with the following fields. Read `references/rtm-fields.md` for detailed descriptions and examples of each field.

### Required Fields (always include these)

1. **Requirement ID** - Unique identifier (e.g., REQ-001, REQ-002)
2. **Source Reference** - Exact clause, section, rule, or schedule reference from the source document (e.g., "Schedule 1, Rule 3.2", "Section 14(2)(b)", "Clause 7.1.1")
3. **Source Document** - Name and version/date of the regulatory document
4. **Verbatim Text** - The exact text from the regulation, copied word for word. No paraphrasing, no shortening. This is the single source of truth
5. **Plain English Summary** - What this requirement actually means in simple, jargon-free language that a non-specialist could understand. Write as if explaining to someone who has never read the regulation
6. **Source Type** - One of: VERBATIM, DERIVED, ASSUMED, INTERPRETED (see table above)
7. **Business Domain** - Which area of the business this applies to (e.g., Billing, Metering, IT Systems, Customer Communications, Market Operations, Settlement, Registration, Compliance, Legal, Finance, Network Operations, Data Management)
8. **Obligation Type** - What kind of obligation this creates:
   - **MUST DO** - Mandatory requirement, no choice
   - **MUST NOT DO** - Explicitly prohibited
   - **MAY DO** - Permissive, optional
   - **CONDITIONAL** - Only applies if certain conditions are met
   - **REPORTING** - Requires reporting or disclosure
   - **RECORD KEEPING** - Requires maintaining records
   - **TIMELINE** - Specifies a deadline or timeframe
9. **Priority** - Based on obligation type and consequences:
   - **CRITICAL** - Non-compliance has severe consequences (penalties, licence risk, safety)
   - **HIGH** - Mandatory requirement with significant impact
   - **MEDIUM** - Important but with less severe consequences
   - **LOW** - Minor or permissive requirements
10. **Compliance Status** - Current state (defaults to NOT ASSESSED for new analysis):
    - NOT ASSESSED, COMPLIANT, PARTIALLY COMPLIANT, NON-COMPLIANT, NOT APPLICABLE, IN PROGRESS
11. **Effective Date** - When this requirement comes into effect (if specified in the document)

### Recommended Fields (include when possible)

12. **Responsible Party** - Who within the organisation is likely responsible (if determinable from the regulation, e.g., "Registered Participants", "Retailers", "Network Service Providers")
13. **Dependencies** - Other requirements that this one depends on or is linked to (e.g., "REQ-003 must be met before this can be implemented")
14. **Change Type** - For amendments and rule changes:
    - **NEW** - Brand new requirement
    - **AMENDED** - Modification of an existing requirement
    - **DELETED** - Requirement being removed
    - **UNCHANGED** - Existing requirement not affected by this change
15. **Implementation Notes** - Any practical considerations for implementing this requirement
16. **Verification Method** - How compliance with this requirement would be verified:
    - **INSPECTION** - Review of documents or records
    - **TESTING** - Active testing of systems or processes
    - **DEMONSTRATION** - Showing that a process works
    - **ANALYSIS** - Analytical assessment
17. **Risk if Non-Compliant** - What happens if this requirement is not met (penalties, sanctions, licence conditions, safety risks)

## How to Analyse a Regulatory Document

Follow this process when the user provides a regulatory document:

### Step 1: Understand the Document
- Read the entire document (or section provided) carefully
- Identify what type of document it is (new legislation, amendment, rule change, standard, policy)
- Note the issuing authority and effective dates
- Identify who the document applies to (which types of organisations or roles)

### Step 2: Extract Requirements Systematically

**THE #1 RULE: CAPTURE EVERYTHING. DO NOT SKIP ANYTHING.**

It is far better to include a requirement that turns out to be minor than to miss one that turns out to be critical. You are not the judge of what matters to the user's business. A clause that seems like a trivial administrative detail could be the one that triggers a compliance breach or audit finding. Extract it all and let the humans decide what's important.

**What to extract:**
- Every "shall", "must", "will", "is required to", "is obligated to" as a mandatory requirement
- Every "must not", "shall not", "is prohibited from" as a prohibition
- Every "may", "can", "is permitted to" as a permissive requirement
- Every "should" as a recommended practice (flag as DERIVED with note about "should" vs "must")
- Every definition that creates or modifies an obligation (definitions sections are full of hidden requirements)
- Every transitional provision, commencement date, or phased implementation detail
- Every record-keeping or documentation requirement, even if mentioned in passing
- Every reporting obligation, notification requirement, or disclosure duty
- Every timeframe, deadline, or period mentioned (even "as soon as practicable" counts)
- Every reference to penalties, enforcement, or consequences of non-compliance
- Every exception, exemption, or carve-out (these are just as important as the obligations themselves because they define the boundaries)
- Every cross-reference to other legislation, rules, or standards (flag these as needing separate review)
- Every governance requirement (board approval, committee oversight, delegation authorities)
- Every requirement buried in notes, footnotes, explanatory provisions, or schedules
- Implied requirements that aren't stated with obligation words but are clearly necessary for compliance

**How to extract:**
- Go through the document **sequentially, section by section, clause by clause**
- Do NOT jump around or cherry-pick what looks important
- Do NOT skip preambles, purpose statements, or scope sections as they often contain binding obligations or critical context that changes how other clauses should be interpreted
- Do NOT skip schedules, appendices, annexures, or attachments as these often contain the most detailed operational requirements
- Do NOT assume "administrative" or "procedural" clauses are unimportant
- If a single clause contains multiple obligations, extract each one as a separate requirement with its own row
- If you are unsure whether something is a requirement, include it and flag it with a note explaining your uncertainty

**After completing your extraction, do a completeness check:**
- Count the sections/clauses in the source document
- Verify you have at least one requirement from each substantive section
- If any section yielded zero requirements, go back and re-read it. Either it genuinely contains no obligations (rare) or you missed something
- List any sections you did not extract from and explain why (e.g., "Section 1 - Preliminary: contains definitions only, all captured under relevant requirement rows")

### Step 3: Categorise and Enrich
- Assign each requirement to the appropriate business domain
- Determine obligation type and priority
- Write the plain English summary for each
- Identify dependencies between requirements
- Flag any ambiguities or areas where interpretation was needed

### Step 4: Quality Check
Before presenting the RTM, verify:
- **Completeness audit** - Cross-check every section, clause, and schedule of the source document against your extracted requirements. If a section has no requirements extracted, explicitly state why
- Every requirement has a valid source reference that can be looked up in the original document
- Verbatim text is genuinely verbatim (not paraphrased)
- Plain English summaries don't introduce meaning that isn't in the original text
- Source type flags are honest (don't mark DERIVED requirements as VERBATIM)
- Business domain assignments make sense
- No requirements were missed (especially in schedules, appendices, definitions, transitional provisions, footnotes, and explanatory notes)
- ASSUMED entries clearly explain the reasoning
- Single clauses with multiple obligations have been split into separate requirements
- Exceptions and exemptions have been captured as standalone requirements (not just mentioned in passing)

### Step 5: Present the Summary
Before the detailed matrix, always provide a high-level summary that includes:
- Document title, issuing authority, and effective date
- Total number of requirements extracted (broken down by source type)
- Count by obligation type (how many MUST DO vs MAY DO etc.)
- Count by priority level
- Count by business domain
- **Coverage map** - A list of every section/part/schedule in the source document with the number of requirements extracted from each. Any section showing zero requirements must have an explanation (e.g., "Part 1 - Preliminary: 0 requirements - contains only interpretation provisions, definitions captured within relevant requirement rows"). This gives the user confidence that nothing was skipped
- Any key concerns, ambiguities, or areas flagged for human review
- Any limitations of the analysis (e.g., sections that couldn't be read, cross-references to other documents not provided)

## Output Format

This skill is **output-format agnostic**. The analysis and structure are the same regardless of how the user wants the output. Ask the user how they want the output if they haven't specified. Common options:

- **Confluence page** - Use the confluence-beautiful-pages skill if available for professional formatting with coloured headers, status lozenges, and panels
- **Word document (.docx)** - Use the docx skill for a professional document with tables
- **Excel spreadsheet (.xlsx)** - Use the xlsx skill for a filterable, sortable spreadsheet (often preferred for large RTMs)
- **In chat** - Present as formatted tables in the conversation

For very large documents (50+ requirements), recommend Excel or splitting across multiple pages/documents for manageability.

## Handling Large Documents

For regulatory documents over 30 pages:
- Process in sections rather than all at once
- Start with a summary/overview pass, then do detailed extraction section by section
- Group requirements logically (by section of the regulation, or by business domain)
- For Confluence output, split into a parent page with summary and child pages by section or domain
- For Excel, use separate worksheets for each section or domain, plus a summary worksheet

## Important Warnings

- **CAPTURE EVERYTHING.** This is the most important rule. Do not self-filter. Do not skip clauses because they look administrative, procedural, or unimportant. A requirement that seems trivial to AI could be the exact clause an auditor asks about. Include it and let the human decide what matters. It is always better to have a row in the matrix that turns out to be low priority than to have a gap that turns out to be a compliance breach
- **Never invent requirements.** If it's not in the document (explicitly or by clear implication), don't include it. If you think something is missing, flag it as ASSUMED and explain your reasoning
- **Never change verbatim text.** The verbatim column must be an exact copy. If there are typos in the regulation, copy the typos
- **Always flag uncertainty.** If you're unsure about an interpretation, say so. Add a note like "This clause is ambiguous. The interpretation above assumes X, but it could also mean Y"
- **Cross-references matter.** If the regulation references another document you haven't been given, flag this as a standalone requirement noting the cross-reference. Don't guess what the referenced document says
- **Definitions matter.** Regulatory documents often have specific definitions that change the meaning of common words. Always check the definitions section and apply those definitions. If a definition itself creates an obligation or narrows scope in a meaningful way, extract it as a requirement
- **Don't over-derive.** Be conservative with DERIVED requirements. Only include them when they are clearly and logically necessary to comply with a VERBATIM requirement
- **Exceptions are requirements too.** An exemption, carve-out, or exception is just as important as the obligation it modifies. If a clause says "except where X applies", that exception needs its own row
- **Footnotes and explanatory notes can contain obligations.** Don't skip them. Some regulators put critical detail in footnotes or explanatory provisions that look like commentary but actually contain binding requirements
- **If the document is too large to process in one pass, tell the user.** Say which sections you've covered and which are still pending. Never silently skip sections
