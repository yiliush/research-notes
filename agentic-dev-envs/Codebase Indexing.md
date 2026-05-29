---
tags: [concept, infrastructure]
created: 2026-05-28
---

# Codebase Indexing

Frontier LLMs have context windows in the millions of tokens by mid-2026, but no production agent loads an enterprise monorepo into context. Codebase indexing is the layer between "this codebase has 8M lines of code" and "give the model exactly the 4,000 tokens relevant to this query." Every serious ADE vendor has built or licensed a codebase indexer. The architectural choices — embeddings vs. AST vs. lexical, full index vs. lazy fetch, freshness model — define how the agent feels in everyday use.

## The Three Ingredient Types

**Embeddings (semantic retrieval).** Code chunks are embedded into vectors; queries are embedded; nearest-neighbor search returns semantically similar chunks. Captures "show me code that does similar things" but is fuzzy on identifiers, fails on rare tokens, and re-indexes on every change.

**AST / symbol-level (structural).** Parse code into ASTs, build a symbol graph (definitions, references, call graphs, type information). Captures "where is this function defined and used?" precisely but requires a working parser per language and degrades on broken code.

**Lexical (keyword / regex).** Fast, deterministic, exact. Ripgrep semantics at scale. Captures identifier matches with zero ambiguity but has no understanding of "similar."

Production indexers combine all three. The hybrid retrieval reranks results from each channel.

## Cursor's Approach (Merkle-tree + embeddings)

Cursor's indexer is the most-documented (Cursor blog, "Securely indexing large codebases").

- On open, Cursor walks the repo and builds a **Merkle tree** of cryptographic hashes — each leaf is a file hash, each internal node hashes its children.
- Code is **chunked locally** into semantically meaningful pieces before any network egress.
- Chunks are embedded via OpenAI's API or proprietary models, producing vectors keyed by chunk hash.
- Embeddings + metadata (line numbers, obfuscated file paths) live in **Turbopuffer**, Cursor's remote vector DB. Raw source is not stored remotely.
- On edit, only the file's hash changes — and propagates up the Merkle tree. Cursor compares Merkle roots client/server and syncs only the divergent leaves.
- Indices refresh on a 5-minute cadence by default.

Why it matters: cheap incremental sync (touching one file syncs O(log N) hashes), strong privacy posture (chunks rather than raw files, obfuscated paths), and a vector cache keyed by content hash that survives rebuilds.

## Sourcegraph's Approach (search-anchored)

Sourcegraph built a code-search platform first (2013-onwards) and added the AI layer on top. Cody's RAG architecture:

- The Sourcegraph search engine handles symbol-level precision, regex, and structural queries.
- An embeddings index sits alongside, optional and configurable per repo.
- Retrieval is **search-first**: Cody runs a structural / lexical query (often inferred from the prompt), then optionally reranks with embeddings.
- Index storage is in managed object storage; embedding generation routes to a configurable external service.
- Cody offers "universal codebase context" across multiple repos for enterprise customers — pre-indexed graphs, not per-edit syncs.

Why it matters: ten years of search-engine work means symbol queries are fast, precise, and scale to multi-monorepo enterprises. The tradeoff is heavier infrastructure than embeddings-only.

## Greptile's Approach (AST + graph)

Greptile built specifically for codebase Q&A and PR review. Their indexer is more structural:

- Code is parsed into AST; symbols are connected into a call graph.
- The graph is the retrieval substrate — "tell me about function X" walks the call graph rather than running NN search.
- Embeddings supplement for natural-language queries.

Why it matters: structural retrieval gives more accurate answers for "explain this codebase" and "what calls this function" — Greptile's wedge into PR review and architectural docs.

## The Cost / Freshness Tradeoff

Codebase indexing has three pressures that trade against each other:

1. **Index cost.** Embedding 8M LoC at $0.00001/token runs into thousands of dollars per repo. Re-indexing is wasteful.
2. **Freshness.** Stale indices return stale results. The agent rewrites a function, then queries — and gets the old version.
3. **Latency.** Synchronous indexing blocks the user; async indexing creates the freshness problem.

Common mitigations:
- **Content-hashed embeddings (Cursor).** Cache the vector by chunk hash so identical content across branches / repos / rewrites hits the cache.
- **Hybrid retrieval.** Lexical / AST channels handle high-precision recent edits; embeddings handle semantic search and may lag.
- **Incremental Merkle sync.** Only re-embed the files that changed.
- **5-minute polling cadence (Cursor).** The default. Tradeoff between freshness and request volume.

## What's changing in 2026

**Long-context as partial substitute.** With 1M-2M token context windows on Gemini 2.5/3 and Claude Sonnet 4.6 + Mythos, some agents skip indexing for small-to-mid repos entirely. Aider's "repo map" is a token-budgeted symbol summary rather than a true index. Claude Code uses Read + Grep + Glob primitives and a planning loop rather than a precomputed index.

**RAG vs. agentic retrieval.** Cline's plan/act and Claude Code's todo+subagent loops show that an agent that knows how to search lexically (ripgrep), navigate (LSP), and read selectively can match a precomputed embeddings index on many tasks. This is shifting some vendor investment away from indexing and toward better retrieval tools.

**Per-repo cost ceilings.** Vendors are now publishing per-repo index cost SLAs in enterprise contracts. Indexing a 10M-line monorepo at acceptable freshness is a measurable expense (~$10k-$100k/yr equivalent at vendor margins).

## Which vendor uses what

| Vendor | Primary technique | Secondary | Storage |
|---|---|---|---|
| Cursor | Merkle + embeddings | LSP, ripgrep | Turbopuffer |
| Cody (Sourcegraph) | Search-anchored AST + lexical | Embeddings | Managed object storage |
| Greptile | AST + call graph | Embeddings | Proprietary |
| Augment Code | Custom context engine, monorepo-tuned | Symbol graph | Proprietary |
| Claude Code | Agentic (Read/Grep/Glob, no precomputed index) | Long-context | None |
| Aider | Repo map (symbol summary) | Long-context | In-memory |
| Cline | Agentic retrieval, MCP-extensible | Long-context | None |

## See Also
- [[Agent Harness]]
- [[Model Context Protocol (MCP)]]
- [[Market Structure and Value Chain]]
- [[Competitive Dynamics]]
