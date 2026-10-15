# Repolex Knowledge Graph of simonw/strip-tags

RDF knowledge graph data for [simonw/strip-tags](https://github.com/simonw/strip-tags), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/strip-tags
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 868072957a9502a741b1ca947a992a988f58dc2e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 868072957a9502a741b1ca947a992a988f58dc2e
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 311e790dc1058e32276163929ba0273c0e4d5497.nq.gz
│   ├── 399c217744c595da6a67cdbaa3a321a13db1d63b.nq.gz
│   ├── 40fd13d18b512b626c1eeb645de7fec05fdec4b4.nq.gz
│   ├── 4bc3272f33b879bed5b214aa964de0f919a00c30.nq.gz
│   ├── 53605b7a5ec51bc95dca4fb43fdb350bf9362435.nq.gz
│   ├── 904c0ba68e8ccd53c921ef38b1005a091c2e161d.nq.gz
│   ├── 98dcca0c2836ae53d67260be8a5431b855e461bb.nq.gz
│   ├── 9d9705d2bf561c2a3e0ad6229f842d0a11e52668.nq.gz
│   ├── b1470a2f1b53ec7d2df9fdd7cf5f175aecfd677f.nq.gz
│   ├── b780e5bed42852df5c233a71bfa53ec023970b7a.nq.gz
│   ├── bd61e6f70cc08185f2f7dd13deaa9c6949e1872a.nq.gz
│   └── d31cca8ac468f4a39f0edac7dd9df33d085ecae7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 868072957a9502a741b1ca947a992a988f58dc2e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[simonw/strip-tags](https://github.com/simonw/strip-tags)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
