# Research Before Coding - Claude Context

This is a standalone Claude Code skill repository.

## Purpose

Enforces mandatory research with WebSearch and optional context7 before ANY implementation code.

## Quick Start

When you want to use this skill in a project:
1. Reference it: `Use ~/.claude/skills/research-before-coding`
2. Or copy to your project's `.claude/skills/` directory

## Testing the Skill

To test if this skill works correctly, use this prompt:

```
I need to add user authentication to a React application using Next.js.
Use the research-before-coding skill and show me exactly what research you perform.
```

**Expected behavior:**
1. Claude loads the skill
2. Runs 3 WebSearch queries in parallel
3. Optionally runs 1 context7 lookup for the library (if available)
4. Synthesizes findings before suggesting any code

## Structure

```
.claude/skills/research-before-coding/
├── SKILL.md           # Main skill definition
└── query-patterns.md  # Query templates and examples
```
