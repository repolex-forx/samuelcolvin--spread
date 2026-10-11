# Repolex Knowledge Graph of samuelcolvin/spread

RDF knowledge graph data for [samuelcolvin/spread](https://github.com/samuelcolvin/spread), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/spread
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 180cfaccbcc0304233cfb6e8417c5c82641df59b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 180cfaccbcc0304233cfb6e8417c5c82641df59b
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ae460e9fbc26bb8b220d59f954c6d28c78aa1bf.nq.gz
│   ├── 0c6e2927e99c3cee27ceca5ca366b617b9838429.nq.gz
│   ├── 251a662853bcd05e26d706d92a3e398ea0554e38.nq.gz
│   ├── 29061c174ed5ffa176c80a2baa53a1cb9f72f9a9.nq.gz
│   ├── 41c4e6a3619a531c7039d710a6bb0bd89ef49e2e.nq.gz
│   ├── 41d9b88c46f14176f39f5e2d887fa6f244aafb0e.nq.gz
│   ├── 47dc3e3d863cfb5727b87d785d09abf9743c0a72.nq.gz
│   ├── 523119b38f77bdc3f6a63e9281eb62e55439e9b9.nq.gz
│   ├── 56e7cb3e019a715a636ec0bbb15fbbf3266ea6d8.nq.gz
│   ├── 5796f9a68385a3b7b891fa6168cec624ac44c6f1.nq.gz
│   ├── 5b6a64e428e9d380f756875a5542c85da4a34947.nq.gz
│   ├── 6caffce8fcc13be6ebfb1db6e0e8dd943024208c.nq.gz
│   ├── 6dc19e6bc68333d1961085374008f8ac638a3c7e.nq.gz
│   ├── 71fb76ce767c7d2a713f44da2f5ef01dd7d3fd04.nq.gz
│   ├── 8fee07bd373d95b6f2fe3affa72f6aca6fd81998.nq.gz
│   ├── 922de720e039488deea7e723e1008559472d0bdd.nq.gz
│   ├── a7c824045fd26f9b1191a7b23d0efec7ed8b3ef4.nq.gz
│   ├── a84beba6fb2dc2ea5d7e2a2123846fdf950d2890.nq.gz
│   ├── ab8fbe91fcb9933348201125313246a3cb0be566.nq.gz
│   ├── b97b210e35aa202e8c76cacc5e15c3e39fb9cadc.nq.gz
│   ├── c82329421d4327f8e24469b4fda983937d65081c.nq.gz
│   ├── d7173c6cf5ec436755409b87344826a8e7250822.nq.gz
│   ├── de645bfaf264a1ceb04fda03009408f6393100ac.nq.gz
│   ├── de9730c5e9747be215921cae70ef7d5c7b0cc147.nq.gz
│   ├── e30fd6b46811d41fa637a1900d57d62d5c34dcf1.nq.gz
│   ├── e48f502972af962e56df6551f199e5bb9b8b9227.nq.gz
│   ├── e5043e862ef828582de35dafc7a2e676cc4c411d.nq.gz
│   └── fbeaa0230ea00f3ea1e1ab6011f73e759793d8d3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 180cfaccbcc0304233cfb6e8417c5c82641df59b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[samuelcolvin/spread](https://github.com/samuelcolvin/spread)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
