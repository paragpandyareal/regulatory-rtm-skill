# Regulatory Requirements Traceability Matrix (RTM) Skill

A Claude AI skill that analyses regulatory documents and produces comprehensive Requirements Traceability Matrices, mapping every obligation to its source with full transparency about what is verbatim from the document vs what has been derived or assumed.

## The Problem

When you get a new regulation, rule change, or compliance standard, you need to figure out what it actually requires. That means reading dense legal language, extracting every obligation, understanding who it applies to, and translating it into something your business teams can actually work with. This is slow, error-prone, and easy to miss things.

## The Solution

This skill instructs Claude to go through a regulatory document clause by clause and extract every single obligation into a structured matrix. Nothing gets skipped, even if it seems minor, because a clause that looks administrative could be the exact one an auditor asks about.

### What Makes This Different

- **Verbatim text preserved** - The exact regulatory wording is captured word for word, so you always have the source of truth
- **Plain English translations** - Every requirement gets a jargon-free explanation that anyone can understand
- **Honesty about sources** - Every entry is flagged as VERBATIM (exact text), DERIVED (logically implied), INTERPRETED (ambiguous language), or ASSUMED (not in the document but likely needed). You always know what came from the regulation vs what Claude figured out
- **Coverage map** - A section-by-section audit showing how many requirements were extracted from each part of the document, so you can see at a glance that nothing was skipped
- **Output-format agnostic** - Works with Confluence, Word, Excel, or just in chat

### Fields Captured

Every requirement gets these fields:

- Requirement ID
- Source Reference (exact clause/section number)
- Source Document
- Verbatim Text
- Plain English Summary
- Source Type (VERBATIM / DERIVED / INTERPRETED / ASSUMED)
- Business Domain (billing, metering, IT systems, etc.)
- Obligation Type (MUST DO, MUST NOT DO, MAY DO, CONDITIONAL, REPORTING, RECORD KEEPING, TIMELINE)
- Priority (CRITICAL, HIGH, MEDIUM, LOW)
- Compliance Status
- Effective Date
- Plus optional fields for responsible party, dependencies, change type, verification method, and more

## Installation

### Claude Code

**Option 1 - Clone into your skills directory:**

```bash
git clone https://github.com/paragpandyareal/regulatory-rtm-skill.git
cp -r regulatory-rtm-skill ~/.claude/skills/regulatory-rtm
```

**Option 2 - Use --add-dir:**

```bash
git clone https://github.com/paragpandyareal/regulatory-rtm-skill.git
claude --add-dir /path/to/regulatory-rtm-skill
```

### Claude.ai (Web/Desktop)

1. Download this repository as a ZIP file (click the green "Code" button on GitHub, then "Download ZIP")
2. In Claude.ai, go to **Settings > Capabilities** and make sure "Code execution and file creation" is enabled
3. Go to **Customize > Skills**
4. Click the **"+"** button, then **"+ Create skill"**
5. Upload the ZIP file
6. Toggle the skill on

## Usage

Upload a regulatory document (PDF, Word, or paste the text) and ask Claude to analyse it:

- "Analyse this regulation and create a requirements traceability matrix"
- "Extract all the obligations from this rule change document"
- "What does this regulation require us to do? Give me everything, don't skip anything"
- "Create an RTM from this document and output it as an Excel spreadsheet"
- "Break down this legislation into plain English requirements for our compliance team"

### Output Formats

The skill works with whatever output format you need:

- **Confluence** - Pairs with the [confluence-beautiful-pages](https://github.com/paragpandyareal/claude-confluence-beautiful-pages) skill for professional formatting
- **Excel (.xlsx)** - Great for large RTMs that need filtering and sorting
- **Word (.docx)** - For formal compliance documentation
- **In chat** - For quick reviews

## What's Included

```
regulatory-rtm-skill/
├── SKILL.md                    # Main skill instructions
├── references/
│   └── rtm-fields.md           # Detailed field descriptions and examples
├── LICENSE                     # Apache License 2.0
├── README.md                   # This file
└── CONTRIBUTING.md             # How to contribute
```

## Requirements

- **Claude Pro, Max, Team, or Enterprise plan** - Skills require a paid Claude plan
- **Code execution enabled** in Claude.ai (Settings > Capabilities)

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the Apache License 2.0. See [LICENSE](LICENSE) for details.

You are free to use, modify, and distribute this skill. Attribution is required.

## Credits

Created by [Parag Pandya](https://github.com/paragpandyareal).

Built from real-world experience extracting and tracing regulatory requirements in the Australian energy sector.
