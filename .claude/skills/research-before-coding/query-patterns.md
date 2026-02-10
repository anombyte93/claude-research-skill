# Query Patterns for Research

Quick reference for formulating effective research queries within the **research agent**.

## WebSearch Query Templates

These are used INSIDE the Task agent prompt. The agent runs them via the WebSearch tool and distills the output.

### For New Features
```
"best practices <language/framework> <feature type> 2026"
```
Examples:
- `"best practices react authentication flow 2026"`
- `"best practices python async api design 2026"`

### For Architecture Decisions
```
"<technology> architecture patterns <domain>"
```
Examples:
- `"nextjs architecture patterns e-commerce"`
- `"fastapi architecture patterns microservices"`

### For Implementation Examples
```
"github <technology> <use case> examples"
```
Examples:
- `"github python web scraping real examples"`
- `"github typescript state machine implementation"`

### For Bug Fixes
```
"<error message or symptom> <technology> fix 2026"
```
Examples:
- `"sqlite database is locked python fix 2026"`
- `"react useEffect infinite loop causes 2026"`

### For Library Selection
```
"<task> <language> library comparison 2026"
```
Examples:
- `"python http client library comparison 2026"`
- `"javascript testing framework comparison 2026"`

## context7 Query Templates (Main Session Only)

**IMPORTANT:** context7 is used in the **main session** after the research agent returns, for lightweight API doc lookups. Do NOT put context7 calls inside the research agent.

### Step 1: Resolve Library
Use Claude Code's `resolve-library-id` tool:
```json
{"libraryName": "<library-name>", "query": "<what you need help with>"}
```

### Step 2: Query Docs
Use Claude Code's `query-docs` tool:
```json
{"libraryId": "<id-from-step-1>", "query": "<your question>"}
```

### Common context7 Queries
- `"how to <use feature>"`
- `"authentication example"`
- `"error handling"`
- `"configuration options"`
- `"API reference <method name>"`

## CALLER NEEDS TO KNOW Examples

The most important part of the research agent prompt is the `CALLER NEEDS TO KNOW` field. Good examples:

| Scenario | CALLER NEEDS TO KNOW |
|----------|---------------------|
| Adding auth | "How to implement OAuth in Next.js 14 with NextAuth v5, including session management" |
| Fixing a bug | "Why SQLite throws 'database is locked' during concurrent writes and how to fix it" |
| Choosing a library | "Which Python HTTP client to use for async API calls with retry logic" |
| Performance issue | "How to optimize React re-renders in a large data table with 10k+ rows" |
| New feature | "How to implement WebSocket real-time updates in a FastAPI backend" |

Be specific. The more precise this field is, the more focused the distilled output will be.

## Query Optimization Tips

1. **Always include year** - "2026" ensures current results
2. **Use "best practices"** - surfaces established patterns
3. **Include github** - gets real working code examples
4. **Be specific** - "react authentication" not "authentication"
5. **Mention error exactly** - copy-paste error messages for bugs
