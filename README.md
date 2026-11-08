# Repolex Knowledge Graph of bentoml/rag-tutorials

RDF knowledge graph data for [bentoml/rag-tutorials](https://github.com/bentoml/rag-tutorials), parsed by [repolex](https://repolex.ai).

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
rlex download bentoml/rag-tutorials
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f241f888a356888ff6ca2e5c7726d542dadb0f35
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f241f888a356888ff6ca2e5c7726d542dadb0f35
│           └── chunk-001.nq.gz
├── blob
│   ├── 2849ed239f6006f1cac4cbc92afae768e0071b53.nq.gz
│   ├── 29d55110f5339fbae233d38b8c18b479cee78532.nq.gz
│   ├── 308fafa77e6b403500bb7848d9dbb5bf72d05788.nq.gz
│   ├── 66e166ba093b01544285c7ada05c18dc930cd059.nq.gz
│   ├── 6ebd858793994d7f1299411dc5c8a582ca4a1175.nq.gz
│   ├── 702834826f5ec375e6cbfe1bde598193956842f8.nq.gz
│   ├── 731e082f7e4c5030331dc7b309684e487aa3b991.nq.gz
│   ├── 7e40a0093cd80c467ac810151b30f5a5ddba8685.nq.gz
│   ├── 82f4325bbf7112bee8172fffa31e701cebe4db20.nq.gz
│   ├── 8ee6dbfad51665e8f7f6ce489443cc9ac9b1a9a8.nq.gz
│   ├── 905b1a6f4129cd8944b63539dd6c95c34cc892f6.nq.gz
│   ├── 9a93d8795991fe888e171e72931337862f936a8f.nq.gz
│   ├── 9c1803d41aa1fad5c302b462493d52da9759513f.nq.gz
│   ├── ad1876085e156c2d0bcf298078ba0a9c8ed8a4da.nq.gz
│   ├── b07cc45ff21fe213a8709bcdc5fbb534d577bc3a.nq.gz
│   ├── b21e6f36175b8d0683c668aed122efd5f9bd9812.nq.gz
│   ├── b89aeccee73d4006fd9de1808a00b1f817f1c4ca.nq.gz
│   ├── bc277ca98ebb0f66c37e4ca4d4c0a4604f561cc6.nq.gz
│   ├── bc9694fd57e74ed7e0e81b47d564c27634f5977d.nq.gz
│   ├── bf0b4b44e0ccc5f45a8c70473fb30067b0c51b5d.nq.gz
│   ├── d100db9968f3fbc77a61c8352bb2d8076710ebc8.nq.gz
│   ├── d768e6121b9a21cc96cbab3bda43d322d4b2a801.nq.gz
│   ├── d9cf1150b84cca06b20e7dcae3a5941ad67e1d87.nq.gz
│   ├── e44057592c4cc51a1128a86e3150c062add3bce2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f69b259ebf9b0c66bdaa2ba38198c7d180cf4aaf.nq.gz
│   └── fd2c5ff75e30d7fc3a8f88eb6ef8fd586b581c84.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f241f888a356888ff6ca2e5c7726d542dadb0f35.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[bentoml/rag-tutorials](https://github.com/bentoml/rag-tutorials)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
