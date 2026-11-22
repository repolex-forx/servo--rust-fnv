# Repolex Knowledge Graph of servo/rust-fnv

RDF knowledge graph data for [servo/rust-fnv](https://github.com/servo/rust-fnv), parsed by [repolex](https://repolex.ai).

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
rlex download servo/rust-fnv
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4b4784ebfd3332dc61f0640764d6f1140e03a9ab
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4b4784ebfd3332dc61f0640764d6f1140e03a9ab.nq.gz
│   └── repolex
│       └── 4b4784ebfd3332dc61f0640764d6f1140e03a9ab
│           └── chunk-001.nq.gz
├── blob
│   ├── 1284119a679f7b7a3c77aee2eabbfcc90933c85d.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 25dd6d5b0d9219ef9a7315c22785586cd1c6d451.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── b58b1064e4ec01a4ac16cc94e72bb1b5240b32ee.nq.gz
│   ├── bc976a272cedb87725d582193a858be931e722d4.nq.gz
│   └── f2df52f631a7bc5c02fea0dba2da8d219b4ebd07.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4b4784ebfd3332dc61f0640764d6f1140e03a9ab.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 16 files
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

[servo/rust-fnv](https://github.com/servo/rust-fnv)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
