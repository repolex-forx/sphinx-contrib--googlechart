# Repolex Knowledge Graph of sphinx-contrib/googlechart

RDF knowledge graph data for [sphinx-contrib/googlechart](https://github.com/sphinx-contrib/googlechart), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/googlechart
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9299aa6cff391f0d36acddc730eeba50c6a68698
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9299aa6cff391f0d36acddc730eeba50c6a68698
│           └── chunk-001.nq.gz
├── blob
│   ├── 0480c5c6bd86cfa1dcbdef4c3d3d1797c79cd03f.nq.gz
│   ├── 1c9291d13796ff647b0975c728d1ff3da57d6715.nq.gz
│   ├── 1dfe7d03f12b93c7f50abee2e71336809800544a.nq.gz
│   ├── 2eba9160d403563d8b100534a4d950281de057e6.nq.gz
│   ├── 45dd5f5b51e10661a6b6699e050c4ab23d721804.nq.gz
│   ├── 724255805f5f169369f13d433f26a2ceadc989c1.nq.gz
│   ├── 72a33558153fb57def85612b021ec596ef2a51b9.nq.gz
│   ├── 8c0405e838ba111d1f495e1078ebc828da831cad.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── 90b1ba0a5fe3a05f84b7f07b1a246a1de2ed3f7e.nq.gz
│   ├── 9ae0e350f99d28fde06662b0fc9656687d659a35.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── b9a653e6d0c0ebb049fc1bbe414e960391dd10c8.nq.gz
│   ├── ceac1765a932e19444f19d3fdd6f26f618bea1b7.nq.gz
│   └── d6d37cf967830d976ee1dfccf9265a476f85b209.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9299aa6cff391f0d36acddc730eeba50c6a68698.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 21 files
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

[sphinx-contrib/googlechart](https://github.com/sphinx-contrib/googlechart)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
