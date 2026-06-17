---
name: xquik-source-research
description: Use when a task needs a sourced public X data packet for research, monitoring, market context, content review, or social evidence collection. This skill routes agents through Xquik REST, MCP, or the x-developer TypeScript package and returns cited, bounded, timestamped source notes instead of unsourced summaries.
license: MIT
---

# Xquik Source Research

Use this skill when an agent needs public X evidence that can be checked later. Keep the result narrow, cited, and bounded.

## Source Truth

- Docs: `https://docs.xquik.com/api-reference/overview`
- X API guide: `https://docs.xquik.com/alternatives/x-api`
- MCP server: `https://xquik.com/mcp`
- TypeScript package: `x-developer`

## Required Inputs

- Research question or claim to check
- Query terms, usernames, tweet URLs, or tweet IDs
- Time window
- Maximum sample size
- Required fields for the downstream task

## Workflow

1. Write a source packet plan before fetching data:
   - `query`
   - `timeWindow`
   - `sampleLimit`
   - `fields`
   - `collectionPurpose`
2. Choose the integration path:
   - Use REST for app or script workflows.
   - Use MCP for agent workflows.
   - Use `x-developer` for TypeScript projects.
3. For REST search, call `GET /api/v1/x/tweets/search` with the `x-api-key` header.
4. Preserve provenance for each item:
   - source URL or tweet ID
   - author handle
   - created timestamp
   - collection timestamp
   - query or route used
5. Normalize the packet into this shape:

```json
{
  "question": "What is being checked",
  "query": "from:example launch",
  "timeWindow": "2026-06-01 to 2026-06-17",
  "collectedAt": "2026-06-17T00:00:00Z",
  "sampleLimit": 25,
  "items": [
    {
      "postId": "123",
      "url": "https://x.com/example/status/123",
      "author": "example",
      "createdAt": "2026-06-10T12:00:00Z",
      "text": "Short cited excerpt or summary",
      "metrics": {
        "likes": 0,
        "reposts": 0,
        "replies": 0
      }
    }
  ],
  "caveat": "Bounded public X sample, not a full population study."
}
```

## Guardrails

- Never include API keys, OAuth tokens, cookies, or private account material in outputs.
- Do not claim the sample represents all X activity.
- Do not infer private demographics or identity traits.
- Keep write actions out of this workflow.
- Retry only on `429` and `5xx`, respect `Retry-After`, and stop after 3 attempts.
- If the task needs an export or longer run, estimate scope first and hand off the exact query.
