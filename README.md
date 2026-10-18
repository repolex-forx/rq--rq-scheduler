# Repolex Knowledge Graph of rq/rq-scheduler

RDF knowledge graph data for [rq/rq-scheduler](https://github.com/rq/rq-scheduler), parsed by [repolex](https://repolex.ai).

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
rlex download rq/rq-scheduler
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 134c2eb1b8c65510bc1b8fdfdbe787decef890f2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 134c2eb1b8c65510bc1b8fdfdbe787decef890f2
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a8df87af1cba513e357c847bdd62decd5e35800.nq.gz
│   ├── 19598d9d677eb4ad419f236f96117e1fc6200313.nq.gz
│   ├── 1f007267fa44ca2c9ba455a82c0f57287b8cf861.nq.gz
│   ├── 25a18fae18b9f70f2e0d0a2a85f879529f15b090.nq.gz
│   ├── 2eb77cf039b33d6be8955d6ef6b04b3f53b0971d.nq.gz
│   ├── 2eede86b8952a6b9e214497231495b489bafa480.nq.gz
│   ├── 3971d066725760c6b3b978c60620503e429783fb.nq.gz
│   ├── 3ba6f05a20dbb07d5a5573b6a1703102271ff658.nq.gz
│   ├── 3c18376c88d96118310ee56848fbc37484f88b04.nq.gz
│   ├── 3d3d36a5402381b48c70e21c3d62dfe91f408e48.nq.gz
│   ├── 4bb40d8047f2405975c65cc1ef53ca8667e11ee1.nq.gz
│   ├── 67ec320eb5eda6efb696ff74418128f2b80fe8b7.nq.gz
│   ├── 803ec5cfd1d026e6e7115554eb251968cd031ff0.nq.gz
│   ├── 9a3128ac658591a2f72dacc9b845647588c12b65.nq.gz
│   ├── 9b22f338b4d0a3f8a7d1e731cad2439565a4cc1b.nq.gz
│   ├── a4108788d319bd6691fb6123689f0923601f214d.nq.gz
│   ├── c34ab026b18f3bd2c489f28484ebe536493aeb2d.nq.gz
│   ├── c6b38618ee3c9689def2dcbdf8898cab350c65a4.nq.gz
│   ├── da9c516dd744b6c88dd8c91f58f7bcf8f7e8341b.nq.gz
│   ├── e0ee78573f38864207e59dcabbbf6c2b5cb163ab.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f130bd08e5c17413daff4de722e1a040381bba01.nq.gz
│   └── f58cb0df067d711a55dfb1b7d8d38ac2a2213ec4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 134c2eb1b8c65510bc1b8fdfdbe787decef890f2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[rq/rq-scheduler](https://github.com/rq/rq-scheduler)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
