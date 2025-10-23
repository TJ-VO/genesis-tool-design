# Contributing to Genesis-Tool

Thank you for your interest in Genesis-Tool!

## Current Status: Not Accepting Contributions

This project is currently **not accepting community contributions** as it is in a strategic development phase. This repository serves for documentation and public disclosure purposes only.

## Why Not Open for Contributions Yet?

**Strategic Development Phase:**
- Core architecture and features are still being finalized
- Project is in active development
- Public release planned under AGPL-3.0

## How You Can Help

While we're not accepting code contributions yet, you can still support the project:

### 1. Provide Feedback
- **GitHub Issues:** Report bugs, suggest features, or ask questions
- **GitHub Discussions:** Share ideas, use cases, or discuss the vision
- Links: https://github.com/TJ-VO/genesis-tool-design/issues

### 2. Spread the Word
- Share the project with others who might benefit
- Discuss the concepts in your communities
- Provide feedback on the documentation

### 3. Stay Updated
- ⭐ Star the repository to follow development
- Watch for updates on the public release

## Future Contributions

**After Public Release:**
- Code contributions will be welcomed under AGPL-3.0
- Contribution guidelines will be published
- Community involvement will be encouraged

---

## Commit Message Guidelines

While contributions are not yet open, these guidelines document the project's commit message conventions for transparency and future reference.

### Format

```
<type>: <subject>

<body>

<footer>
```

### Subject Line

- **Length:** Target ~50 characters (max 72 for clarity)
- **Style:** Imperative mood, present tense ("add" not "added" or "adds")
- **Capitalization:** Lowercase after type prefix
- **No period** at the end
- **Types:**
  - `docs:` Documentation changes
  - `feat:` New features
  - `fix:` Bug fixes
  - `refactor:` Code restructuring without behavior change
  - `test:` Test additions or modifications
  - `ci:` CI/CD pipeline changes
  - `chore:` Maintenance tasks

### Body

- **Length:** Wrap at ~72 characters (soft limit, readability over strictness)
- **Purpose:** Explain *what* and *why*, not *how*
- **Structure:**
  1. First line: Brief explanation of the change
  2. Empty line
  3. Bullet points with specific changes (if multiple)
  4. Optional: Result/impact statement

### Examples

**Simple change:**
```
docs: update README title and section headers
```

**Complex change:**
```
docs: add everyday conversation management use cases

Adds practical use cases demonstrating Genesis' value for regular AI users
beyond specialized professional workflows, with architectural USPs comparing
session-based vs. knowledge-graph approaches.

- Add use case category 7 with 5 detailed scenarios (context pollution,
  template sessions, cross-session search, "what if" exploration, prompt
  template management)
- Add section 6.5 with 6 architectural USPs (context preservation, ancestry
  tracking, selective context, template sessions, cross-session search,
  prompt template management)
- Add section 6.5.1 comparing basic branching vs. knowledge-graph branching
- Include cross-references between competitive-differentiation.md and
  real-world-use-cases.md

Result: Demonstrating architectural advantages for everyday
AI interactions with concrete workflows, metrics, and lessons learned.
```

**With scope:**
```
fix(security): update PBKDF2 iterations to 600k
```

### Tips

- Focus on *why* the change was made, not just *what* changed
- Reference issues/PRs if applicable: `Fixes #123` or `See #456`
- Keep commits atomic (one logical change per commit)
- Write for future maintainers who need to understand the change

---

## Questions?

For questions about this policy or the project:
- **GitHub Issues:** https://github.com/TJ-VO/genesis-tool-design/issues
- **GitHub Discussions:** https://github.com/TJ-VO/genesis-tool-design/discussions

---

**Thank you for your understanding and interest in Genesis-Tool!**