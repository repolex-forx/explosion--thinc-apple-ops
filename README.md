# Repolex Knowledge Graph of explosion/thinc-apple-ops

RDF knowledge graph data for [explosion/thinc-apple-ops](https://github.com/explosion/thinc-apple-ops), parsed by [repolex](https://repolex.ai).

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
rlex download explosion/thinc-apple-ops
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ca926d94f66cdbd2b1d44dbe0987ea0e0f44e264
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ca926d94f66cdbd2b1d44dbe0987ea0e0f44e264
│           └── chunk-001.nq.gz
├── blob
│   ├── 06d42d74a70cc0c7a0a95c02e8d6eefd396ca395.nq.gz
│   ├── 0bec0e1f679f7f44f21b1bd8c5aaa84f593ff2cc.nq.gz
│   ├── 1409ef53914847b4f0e51b6722f3dc512fee7898.nq.gz
│   ├── 2ab09d0ad88bb14ecde558fcbd7b276bc80c5ba0.nq.gz
│   ├── 2eee3f95099badd41cdea40bcfa6fc7fd01ea8fd.nq.gz
│   ├── 3939a6ea55f4bc7968bc0007065dd4bdcedd27e4.nq.gz
│   ├── 3cf07150099b43f21ec576e5009d2f8270fbec3e.nq.gz
│   ├── 4a99eab4f9ae720cc052511b19411c0216131c48.nq.gz
│   ├── 4fdeaf1e992e39254527f0e92b94c349eb0fb491.nq.gz
│   ├── 64608e865630dc56b11fa58df26a536c4a8e7643.nq.gz
│   ├── 7da8330a902f2a7123d81882501066cd1119b5c9.nq.gz
│   ├── 824a592ca6bbd4d748e192ecea9e9414fcf6b56d.nq.gz
│   ├── 91acd6d37b2f4db5a59cd5514df4a55b22b7ceb7.nq.gz
│   ├── 96abb20ef20fe4146e0c4a9ee4a2f11c0f2217f8.nq.gz
│   ├── a49a8909d25e945f8933273116a577a68607c3e6.nq.gz
│   ├── ba2db04cefed0de46ad27940ba9055b2ef376433.nq.gz
│   ├── c03d7320d03796d96bc4a6b7d5212f7d152cfd1e.nq.gz
│   ├── d1c0c464620522edb8dd14947c9f4a586365f859.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ca926d94f66cdbd2b1d44dbe0987ea0e0f44e264.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[explosion/thinc-apple-ops](https://github.com/explosion/thinc-apple-ops)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
