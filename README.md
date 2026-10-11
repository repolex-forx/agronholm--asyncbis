# Repolex Knowledge Graph of agronholm/asyncbis

RDF knowledge graph data for [agronholm/asyncbis](https://github.com/agronholm/asyncbis), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download agronholm/asyncbis
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 592cc0b68355ebc44ad6ffc38309d30df3704f79
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 592cc0b68355ebc44ad6ffc38309d30df3704f79
│           └── chunk-001.nq.gz
├── blob
│   ├── 077e59e546a51ba53446c57d713183a151c25bd4.nq.gz
│   ├── 29f2abcfb3f78539e6167db8ba5bad02fd92dd24.nq.gz
│   ├── 4a7221669ac10a007e33470e9db10a017fe327fc.nq.gz
│   ├── 4e07eecc7e698379a01a3600dfd43a686ff1b52a.nq.gz
│   ├── 5684e8c4e0e28244ad246b44be591f8a09e9a311.nq.gz
│   ├── 67ab1f4b518948efd00155f7d62e878131a20cfe.nq.gz
│   ├── 6ede7a719ee7aba0d51085fcb058d631b9d242ea.nq.gz
│   ├── 8255c4c4ce83d4d641ef2ad9097d68d6143c2ff9.nq.gz
│   ├── 88ab1a7a55a902ae8c67d4e80ca5c051d1ac6536.nq.gz
│   ├── 8935c765fe545993468ed5bb89c94e63300784d6.nq.gz
│   ├── 8ac8c2b0c3d1a9bc743a0d49dbd058428b8ade81.nq.gz
│   ├── b7e2cdbad42b1ac573443e95ad8b801647d3b087.nq.gz
│   ├── bb352f772a914897f03e3c41926f3bb92ceee56c.nq.gz
│   ├── cc8df8a06379b458a1ca46cc5ae86c08688261ea.nq.gz
│   ├── ce04056e113cc6e6dfe05485e693270c4aa38e39.nq.gz
│   ├── d17c36d8340cc7c8a0a3ed500610b766d7a27388.nq.gz
│   └── f9c2936f417bbb07144a29929a12a90721e59d9d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 592cc0b68355ebc44ad6ffc38309d30df3704f79.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 24 files
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
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[agronholm/asyncbis](https://github.com/agronholm/asyncbis)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
