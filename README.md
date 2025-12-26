# .claude

Claude Code Skills for Cursor IDE integration.

## Overview

Collection of Claude Code skills with sync tooling for Cursor IDE. Skills define specialized knowledge domains with frontmatter metadata, reference docs, and rule application triggers.

## Repository Structure

```
.claude/
├── skills/              # Source skills
│   ├── component-scaffolding/
│   ├── component-usage-analysis/
│   ├── css-coder/
│   └── semantic-html/
└── scripts/
    └── sync-skills-for-cursor.sh
```

## Skills

### component-scaffolding

Generates Drupal/Twig component skeletons with web components and Miyagi validation. Includes JSON schema and mock data patterns.

### component-usage-analysis

Analyses component dependencies and usage patterns. Provides search patterns for finding usage, checking removal safety, and auditing dependencies.

### css-coder

CSS authoring guidance emphasizing web standards, accessibility, and performance. Includes patterns for modern CSS syntax, logical properties, and responsive design.

### semantic-html

Well-considered semantic HTML for all users. Emphasizes native HTML elements over ARIA, proper document structure, and accessibility foundations.

## Sync Script

`sync-skills-for-cursor.sh` transforms Claude Code skills to Cursor rule format (`.mdc` files):

- Reads: `.claude/skills/*/SKILL.md` and reference docs
- Writes: `.cursor/rules/*.mdc`
- Converts frontmatter: description → Cursor format with "Apply intelligently" trigger
- Preserves globs for file-based rule application

### Usage

```bash
./scripts/sync-skills-for-cursor.sh
```

## License

MIT - see LICENSE file.
