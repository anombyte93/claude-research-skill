# Research Before Coding

A Claude Code skill that enforces mandatory research using Perplexity API and context7 before writing any implementation code.

## The Core Principle

> **"You don't know anything until Perplexity confirms it"**

This skill treats research as a mandatory first step, not an optional one. No exceptions for "obvious" patterns, "simple" fixes, or things you "know."

## Why?

| Approach | Time Cost |
|----------|-----------|
| **Research first**: 4 parallel calls × 3 seconds = 12 seconds → Correct code |
| **Guess and fix**: Type code → Wrong → Debug → Wrong → Revert → Lost context = 15+ minutes |

## Installation

1. Copy this repository to your skills directory:
   ```bash
   cp -r .claude/skills/research-before-coding ~/.claude/skills/
   ```

2. Or clone and symlink:
   ```bash
   git clone <repo-url>
   ln -s $(pwd)/.claude/skills/research-before-coding ~/.claude/skills/research-before-coding
   ```

## Usage

Invoke the skill before writing any implementation code:

```
/research-before-coding
```

## The Research Workflow

**Step 1: Run 4 Research Queries (ALL in parallel)**

```bash
mcp-cli call perplexity-api-free/search '{"query": "best practices <technology> <task> 2025"}'
mcp-cli call perplexity-api-free/search '{"query": "<technology> architecture patterns <domain>"}'
mcp-cli call perplexity-api-free/search '{"query": "github <technology> <use case> examples"}'
mcp-cli call context7/resolve-library-id '{"library": "<library-name>"}'
```

**Step 2: Synthesize findings**
- Extract key patterns from each source
- Note specific tools/libraries mentioned
- Capture code examples
- Identify conflicts between sources

**Step 3: Document findings**
Write to `CLAUDE-research.md` in your project.

## Requirements

- Claude Code CLI
- `perplexity-api-free` MCP server configured
- `context7` MCP server configured
- `mcp-cli` installed

## License

MIT License - feel free to use and modify for your own workflows.

## Contributing

This is a standalone skill. If you find improvements, submit a PR or fork for your own needs.
