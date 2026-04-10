# Contributing to Regulatory RTM Skill

Thanks for your interest in improving this skill! Contributions are welcome and appreciated.

## How to Contribute

1. **Fork** this repository to your own GitHub account
2. **Clone** your fork locally
3. **Create a branch** for your changes (e.g. `feature/add-gdpr-fields` or `fix/obligation-type-coverage`)
4. **Make your changes**
5. **Test your changes** by using the skill in Claude Code or Claude.ai with a real regulatory document
6. **Submit a Pull Request** back to this repository

## What Makes a Good Contribution

- New RTM fields that are standard in specific industries (e.g., medical devices, financial services, environmental)
- Additional obligation trigger words for different jurisdictions or regulatory styles
- New business domain categories for specific industries
- Improvements to the extraction process that catch more requirements
- Bug fixes where the skill misses certain types of clauses
- Better plain English summary examples
- Additional guidance for handling specific document types (e.g., EU directives, US CFR, Australian NER)

## Pull Request Guidelines

- Describe what you changed and why
- If you're adding new fields or categories, explain the regulatory context
- If you found the skill missed requirements in a real document, describe the gap
- Keep changes focused. One PR per feature or fix is ideal

## What We Won't Accept

- Changes that remove the original attribution or license
- Changes that reduce the completeness of extraction (the skill should always err on the side of capturing more, not less)
- Industry-specific hardcoding that would break the skill for other industries
- Unrelated content or promotional material

## Code of Conduct

Be respectful and constructive. We're all here to make regulatory compliance less painful.

## Questions?

Open an issue if you're not sure whether a change would be welcome.
