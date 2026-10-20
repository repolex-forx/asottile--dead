# Repolex Knowledge Graph of asottile/dead

RDF knowledge graph data for [asottile/dead](https://github.com/asottile/dead), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/dead
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 579345debb8e0a815ffde1a5fc24782a575cac30
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 579345debb8e0a815ffde1a5fc24782a575cac30
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c3cc7c9548af1374c494eb8ef63178e9d8da67e.nq.gz
│   ├── 17fb034d09232911ee3438b325ae3a584e2e055a.nq.gz
│   ├── 32921ea590dad49256c423251224e87643a018ef.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 5a4128de7f16972c216a66cf8d9b13716c1b6111.nq.gz
│   ├── 5e1da823dc675de15ae9dc7adf1f6384368cff18.nq.gz
│   ├── 7945dcf4e88d2793a18ee987b55323a2fe8a078d.nq.gz
│   ├── 8c38c3fa07daab3596dae959bfec1e3571868cb0.nq.gz
│   ├── 96cee8ffa5cfd8240cc0b6afb9c0ff91d33d5537.nq.gz
│   ├── b1447c3015af9511f2dee402ca4b5ad62adf5dce.nq.gz
│   ├── ca1d90ea180858ae143c0e62d920e350d3acc62d.nq.gz
│   ├── e3c45e369338e3a2eb1ed011e48db4bdc4643094.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 579345debb8e0a815ffde1a5fc24782a575cac30.nq.gz
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

[asottile/dead](https://github.com/asottile/dead)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
