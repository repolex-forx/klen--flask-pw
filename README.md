# Repolex Knowledge Graph of klen/flask-pw

RDF knowledge graph data for [klen/flask-pw](https://github.com/klen/flask-pw), parsed by [repolex](https://repolex.ai).

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
rlex download klen/flask-pw
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 04d7846f0c89f2b2331b238b1c8223368c2a40a7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 04d7846f0c89f2b2331b238b1c8223368c2a40a7
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b2e907c89333ea1b1c45cf476f5afdd63c69c08.nq.gz
│   ├── 0fa93532747581302c01061f2ce7aab5bf6a1d53.nq.gz
│   ├── 182745b579c4ef4e673ccd4e470681640f404ffe.nq.gz
│   ├── 1edabfcd6027073dd48aae2ccd295976c1f789c1.nq.gz
│   ├── 3863405b9f0808f51f02f766d6edc06a72dec41b.nq.gz
│   ├── 5b4aaf5a075124b3159bae5ea443bb211839167a.nq.gz
│   ├── 5d7a26d60b5fbd8ed4d6e460a837cd41e02b215c.nq.gz
│   ├── 73f9703b4c852539edd51fc171f6681f4bf29f65.nq.gz
│   ├── 987d344fdb64973b87336998c103ca551893f0a2.nq.gz
│   ├── 9d7bc2bb4548707943a46ff47e2eba786079cf1b.nq.gz
│   ├── 9fef8f6a3bb01d3631f45c736c36ed26129ba58b.nq.gz
│   ├── ab86d3bc8adf697734fb864558f95cb697fe6548.nq.gz
│   ├── bf6289ef0e985490e9ced1676c36ce041b70a774.nq.gz
│   ├── c15b0fced4fe7edc3b8b16a192a21087780a7c52.nq.gz
│   ├── c8d3717f648b43e8ed8fc68c2dba644b3aa5fab5.nq.gz
│   ├── cf4ac590b831d7224020c0fd23d6ba12e1ee9006.nq.gz
│   ├── d35ecd6b83986419370b56fb9238db0da81d36f2.nq.gz
│   ├── d6603942c74523cacf66fb645855534522670b8e.nq.gz
│   └── f47fe37a1ea7f082db232be3959cf26e58b98e7a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 04d7846f0c89f2b2331b238b1c8223368c2a40a7.nq.gz
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

[klen/flask-pw](https://github.com/klen/flask-pw)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
