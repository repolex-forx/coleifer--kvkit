# Repolex Knowledge Graph of coleifer/kvkit

RDF knowledge graph data for [coleifer/kvkit](https://github.com/coleifer/kvkit), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/kvkit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a3551c6fc6bac73ee0a0ab098611d1c9f1b8d089
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a3551c6fc6bac73ee0a0ab098611d1c9f1b8d089
│           └── chunk-001.nq.gz
├── blob
│   ├── 1ad586f43ab33cc11585d4a47d2ab20337db19c7.nq.gz
│   ├── 1d218565dc96112c100601f9cddabaf56d03c910.nq.gz
│   ├── 35310ad3979b62b2dba8069de05e7318dae54931.nq.gz
│   ├── 355c94497b183a23e90c34f929b1ef093b071a15.nq.gz
│   ├── 38a04efe9de16d2c07da41bde3262ed7839e4b81.nq.gz
│   ├── 4076bfeebd00060b0982976bedfbe287cd17e75a.nq.gz
│   ├── 4444c11ed65e775475f8146638266400c685501b.nq.gz
│   ├── 67be722256eada2b59df824040d9a8a371e8c38f.nq.gz
│   ├── 780df0b038f8f5303aa792f18c32453b8a95d3ef.nq.gz
│   ├── 845650d8cc29569266db9c589be2e1ec8f4fe904.nq.gz
│   ├── 95b94544f44335bdd628a35a3ad6d7c447507a78.nq.gz
│   ├── 9c8947c4933fae94f221a01edfc21b4909412942.nq.gz
│   ├── c61cbd1be2deff733af08f906a6847a5b5b80601.nq.gz
│   ├── c7b61cba1580f7222b46e3bffd647181d943b4cc.nq.gz
│   ├── d4a509f45028775d16f075fd4f7fa3dc78296a1f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e7b25139a2b3797f70bd448ab9b57c8bbb111ad4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a3551c6fc6bac73ee0a0ab098611d1c9f1b8d089.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 23 files
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

[coleifer/kvkit](https://github.com/coleifer/kvkit)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
