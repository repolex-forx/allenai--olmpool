# Repolex Knowledge Graph of allenai/olmpool

RDF knowledge graph data for [allenai/olmpool](https://github.com/allenai/olmpool), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/olmpool
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── aa8a3a8b1b1e57bff9d7953ff1daaae05957dcf2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── aa8a3a8b1b1e57bff9d7953ff1daaae05957dcf2
│           └── chunk-001.nq.gz
├── blob
│   ├── 00d6305f127766a996e7ccad55bf73eb08f1eb4c.nq.gz
│   ├── 0c84fa1d786a9d70ed2bd6d7e78f615c207167a7.nq.gz
│   ├── 0e02d34bbaf3c5f822f6620a2243dbd99a3d7f77.nq.gz
│   ├── 0e835994e17cbd0d094e53d7495af7dbb5dc6d8b.nq.gz
│   ├── 1baf804b8509624759d41856e4cd69117cd96371.nq.gz
│   ├── 1dddde0ca2ca8fdd26044f8c17678ffd565dad92.nq.gz
│   ├── 2172ee2ad8458065cdcae7680038d4ba42767343.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 26b1df50e428830827608b043f04c36b903441d4.nq.gz
│   ├── 2ac18af76193a05fc8fdb125cbc3c7142847ad8a.nq.gz
│   ├── 34363932af551d9d5928e2ad2f571d756c4e1184.nq.gz
│   ├── 3c865128e9c468abea9d3b873a4c7976d2df7fc3.nq.gz
│   ├── 46d35dc0d83d8e41e5c98e1a8d8bb2d8fb8055a7.nq.gz
│   ├── 54f8248af4b4b868356e040102b7e2918aa275f6.nq.gz
│   ├── 6f203e9f83b5c85e739fc194f0a4a3b7a55630f9.nq.gz
│   ├── 75e11fedac84ecde992e4e591f5566829a0f5ce8.nq.gz
│   ├── 791f748daee594d6ac628e3b36f40f685e6a27f5.nq.gz
│   ├── 80436ed4ec35988acbaf4bf5309a2edd3c360041.nq.gz
│   ├── 989f8843af72e6984fb353c212442fa219249a68.nq.gz
│   ├── a65e9d9c52bfbac51489ee84e13d59e33d6db7d0.nq.gz
│   ├── a6792910e007a62c3472d39e7db39ed13e7405b0.nq.gz
│   ├── b132dd088f7c2870e52d628490cda4d7edee02eb.nq.gz
│   ├── b54f3bf554e60be7031be5c19f6aa158a0dbe110.nq.gz
│   ├── b80330071db3f160f2de57a31137916a399df814.nq.gz
│   ├── cb3be3516864a221ba2c9e831dc4820913e89cdd.nq.gz
│   ├── d0f640ca3aa9cde0289ede23af010bc2bc041058.nq.gz
│   ├── d9d85bb652c735c6754a98bedfea5f2556807032.nq.gz
│   ├── daf39e7f5d8e2807548bed41a630413394101505.nq.gz
│   └── f0b008a8038e93c55451e9f5ad102cdca91a47d9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── aa8a3a8b1b1e57bff9d7953ff1daaae05957dcf2.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 36 files
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

[allenai/olmpool](https://github.com/allenai/olmpool)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
