# Repolex Knowledge Graph of google-deepmind/jmp

RDF knowledge graph data for [google-deepmind/jmp](https://github.com/google-deepmind/jmp), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/jmp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── df92d9ed2281dd9cef6ad1dbe90fa981aeb4ee83
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── df92d9ed2281dd9cef6ad1dbe90fa981aeb4ee83
│           └── chunk-001.nq.gz
├── blob
│   ├── 07ee5eaca9c6a74d062d6432a7c183252ddd5cf2.nq.gz
│   ├── 197f9bd2b6735309f6937d9483c2e51c11536515.nq.gz
│   ├── 2156784715f8f81403eff16d871f2a33214c653d.nq.gz
│   ├── 2868eac47429a0a0c205a9eae0a282da2b2345ff.nq.gz
│   ├── 2e2dc4d43de7ca645eae9230f2ef8d60c18e13a0.nq.gz
│   ├── 33e076a975e9946a04555edbcc0d2253d4efa0a1.nq.gz
│   ├── 41cf38feb74aab92ac72c3af4b71162dfa641416.nq.gz
│   ├── 4c691ce8758677226e78fd4784618bc19d51a432.nq.gz
│   ├── 544f2913747a9ad03160ce1025843f1d74ff21b6.nq.gz
│   ├── 73a102fe67dc9acd380cc20b1ed62c15be8013d9.nq.gz
│   ├── 81523679eb66d12225e7d41cddd21816de99f181.nq.gz
│   ├── b2573154f55ff6ac4a22a6fb24bb14d78e3bf39e.nq.gz
│   ├── b62b61395d156b95e4748d8f4e041e0241d86062.nq.gz
│   ├── bd162ed3fa9d52fc9b211936d48d97451d380521.nq.gz
│   ├── c3dbb158eda070a18690af986108e5d2682cdd4b.nq.gz
│   ├── c49b32516c10a25d8879ee615938515a0ec35de7.nq.gz
│   ├── ceec6df5deae56786cd867227ac2ca9ff6b38e55.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── dfc892eb9118a05975e604b7cb42e7249f531618.nq.gz
│   └── fe9827681f8c0ae779b1da7ee913332351b4b12c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── df92d9ed2281dd9cef6ad1dbe90fa981aeb4ee83.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[google-deepmind/jmp](https://github.com/google-deepmind/jmp)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
