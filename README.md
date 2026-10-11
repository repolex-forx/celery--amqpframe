# Repolex Knowledge Graph of celery/amqpframe

RDF knowledge graph data for [celery/amqpframe](https://github.com/celery/amqpframe), parsed by [repolex](https://repolex.ai).

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
rlex download celery/amqpframe
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ab4d73d092a8e0d35a7964a2033b8be97ee21a6a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ab4d73d092a8e0d35a7964a2033b8be97ee21a6a
│           └── chunk-001.nq.gz
├── blob
│   ├── 00db2391241976215fed2b589cf77f221492800e.nq.gz
│   ├── 03fff22f9257ccdfb80b61941228fb1764e2c7a2.nq.gz
│   ├── 095fb4b400d998f771265eff2dadfbb6ed7bea34.nq.gz
│   ├── 0b92060db9fbd436a709db8d5a85479a338ce5a9.nq.gz
│   ├── 1c14004c3049b715547d437281a0ded9a98a9331.nq.gz
│   ├── 1c579e7d0639eeeb2ebd3335779789856451969d.nq.gz
│   ├── 1e7df791fbf389ef1d3fbd19026368a785fabdc3.nq.gz
│   ├── 1e9cb042d90bcb60c19acb7199d413e8e2054576.nq.gz
│   ├── 1f4ada1d3a8b74cf480dc2a38c63c4ded5155b17.nq.gz
│   ├── 27ab693a923adc26bf91d06db699d5a2b542dc6c.nq.gz
│   ├── 2ab31ce2fefaa4f01680201083a98604c03d6d63.nq.gz
│   ├── 44b9de1f945699be82aad815e53ddc73c696c690.nq.gz
│   ├── 4f304978fb9deeab5718a1e03b00ed4723291edc.nq.gz
│   ├── 5ba7ea941b228948b15f2332970a9c8fd310bbfd.nq.gz
│   ├── 661e4163edc9163c9409768598d4a059450ef384.nq.gz
│   ├── 6966869c7054c18810eb323772b93ba5a42cefc5.nq.gz
│   ├── 6d2758fd2c593b9ebde9909ec6054bcfbdc94f09.nq.gz
│   ├── 715c03918e68620c7f6d23c3f51958495bcead90.nq.gz
│   ├── a852d167c38b9d66fe308d976a63303027a5df07.nq.gz
│   ├── a9196e42feb3dc6490310dbb68a7132d68c0f6c7.nq.gz
│   ├── b70dcc85cc8f1d7c8fe931d182e550f250e77c2c.nq.gz
│   ├── d7774d218645d56d47c991e63349f2aa60282a52.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f108f2ac895971fe9cd36a5697526114c0f4f565.nq.gz
│   └── f78deff67e321f94a39a7b8b6e483b986d3d335a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ab4d73d092a8e0d35a7964a2033b8be97ee21a6a.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 32 files
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

[celery/amqpframe](https://github.com/celery/amqpframe)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
