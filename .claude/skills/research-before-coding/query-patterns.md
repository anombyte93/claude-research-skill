# Query Patterns for Research

Quick reference for formulating effective research queries.

## Perplexity Query Templates

### For New Features
```
"best practices <language/framework> <feature type> 2025"
```
Examples:
- `"best practices react authentication flow 2025"`
- `"best practices python async api design 2025"`

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
"<error message or symptom> <technology> fix 2025"
```
Examples:
- `"sqlite database is locked python fix 2025"`
- `"react useEffect infinite loop causes 2025"`

### For Library Selection
```
"<task> <language> library comparison 2025"
```
Examples:
- `"python http client library comparison 2025"`
- `"javascript testing framework comparison 2025"`

## context7 Query Templates

### Step 1: Resolve Library
```bash
mcp-cli call context7/resolve-library-id '{"library": "<library-name>"}'
```

### Step 2: Query Docs
```bash
mcp-cli call context7/query-docs '{"id": "<resolved-id>", "query": "<your question>"}'
```

### Common context7 Queries
- `"how to <use feature>"`
- `"authentication example"`
- `"error handling"`
- `"configuration options"`
- `"API reference <method name>"`

## Combined Workflow Examples

### Example 1: Adding Authentication to React App
```bash
# Parallel calls
mcp-cli call perplexity-api-free/search '{"query": "best practices react authentication next-auth 2025"}'
mcp-cli call perplexity-api-free/search '{"query": "nextjs authentication architecture patterns"}'
mcp-cli call perplexity-api-free/search '{"query": "github next-auth oauth examples"}'
mcp-cli call context7/resolve-library-id '{"library": "next-auth"}'
```

### Example 2: Fixing Database Lock Error
```bash
# Parallel calls
mcp-cli call perplexity-api-free/search '{"query": "sqlite database is locked python fix 2025"}'
mcp-cli call perplexity-api-free/search '{"query": "python sqlite connection management best practices"}'
mcp-cli call perplexity-api-free/search '{"query": "github sqlite concurrent access python"}'
mcp-cli call context7/resolve-library-id '{"library": "sqlite3"}'
```

### Example 3: Building API Client
```bash
# Parallel calls
mcp-cli call perplexity-api-free/search '{"query": "best practices python http client api 2025"}'
mcp-cli call perplexity-api-free/search '{"query": "python async http client architecture"}'
mcp-cli call perplexity-api-free/search '{"query": "github httpx aiohttp comparison examples"}'
mcp-cli call context7/resolve-library-id '{"library": "httpx"}'
```

## Query Optimization Tips

1. **Always include year** - "2025" ensures current results
2. **Use "best practices"** - surfaces established patterns
3. **Include github** - gets real working code examples
4. **Be specific** - "react authentication" not "authentication"
5. **Mention error exactly** - copy-paste error messages for bugs
