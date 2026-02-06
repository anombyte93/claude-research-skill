# Query Patterns for Research

Quick reference for formulating effective research queries.

## WebSearch Query Templates

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

## context7 Query Templates (Optional)

**Note:** context7 is optional. If not available, replace with WebSearch queries.

### Step 1: Resolve Library
Use the context7 skill or WebSearch:
- `"context7: <library-name>"` (if skill available)
- `"<library-name> official documentation"` (fallback)

### Step 2: Query Docs
- `"how to <use feature>"`
- `"authentication example"`
- `"error handling"`
- `"configuration options"`
- `"API reference <method name>"`

## Combined Workflow Examples

### Example 1: Adding Authentication to React App
**Run all 3 WebSearch queries in parallel:**
1. `"best practices react authentication next-auth 2025"`
2. `"nextjs authentication architecture patterns"`
3. `"github next-auth oauth examples"`

**Optional context7:**
- `"next-auth"` library documentation

### Example 2: Fixing Database Lock Error
**Run all 3 WebSearch queries in parallel:**
1. `"sqlite database is locked python fix 2025"`
2. `"python sqlite connection management best practices"`
3. `"github sqlite concurrent access python"`

**Optional context7:**
- `"sqlite3"` library documentation

### Example 3: Building API Client
**Run all 3 WebSearch queries in parallel:**
1. `"best practices python http client api 2025"`
2. `"python async http client architecture"`
3. `"github httpx aiohttp comparison examples"`

**Optional context7:**
- `"httpx"` library documentation

## Query Optimization Tips

1. **Always include year** - "2025" ensures current results
2. **Use "best practices"** - surfaces established patterns
3. **Include github** - gets real working code examples
4. **Be specific** - "react authentication" not "authentication"
5. **Mention error exactly** - copy-paste error messages for bugs
