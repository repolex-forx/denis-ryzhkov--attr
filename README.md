# Repolex Knowledge Graph of denis-ryzhkov/attr

RDF knowledge graph data for [denis-ryzhkov/attr](https://github.com/denis-ryzhkov/attr), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download denis-ryzhkov/attr
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 27ae02f3d5f896dbfbce232085bdd7d0e0ded89c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 27ae02f3d5f896dbfbce232085bdd7d0e0ded89c.nq.gz
│   └── repolex
│       └── 27ae02f3d5f896dbfbce232085bdd7d0e0ded89c
│           └── chunk-001.nq.gz
├── blob
│   ├── 07fb6d1712b1a8063f7df057c8f95ee412f907da.nq.gz
│   ├── 1cea6018fed82e3e55e2f78d6acdd80ff5e6465d.nq.gz
│   ├── 32dd1f74ea306eba10f579812c787704ef962520.nq.gz
│   ├── 3d92cd6d632f929650569745aa932ebe1eb7c535.nq.gz
│   ├── 44d9e374bed36021234b5f365d8d214d57827da8.nq.gz
│   ├── 505f79b2ef659fd755980ce3df90f0894f9961ca.nq.gz
│   ├── b1ee433536aa7dda0b01a468b68066e7ce7804a7.nq.gz
│   ├── ced8988416a7766daa4f0c6073c4711c161f7769.nq.gz
│   ├── e66525016b858b18b67ba5f6f70bdae87dbdb1fe.nq.gz
│   └── ff30db39e7c970d8d64128cf98cf169af1162714.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 27ae02f3d5f896dbfbce232085bdd7d0e0ded89c.nq.gz
├── filetree
│   └── 27ae02f3d5f896dbfbce232085bdd7d0e0ded89c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 20 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |

## Source repository

[denis-ryzhkov/attr](https://github.com/denis-ryzhkov/attr)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
