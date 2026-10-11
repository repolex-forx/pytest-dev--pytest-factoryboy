# Repolex Knowledge Graph of pytest-dev/pytest-factoryboy

RDF knowledge graph data for [pytest-dev/pytest-factoryboy](https://github.com/pytest-dev/pytest-factoryboy), parsed by [repolex](https://repolex.ai).

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
rlex download pytest-dev/pytest-factoryboy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 24189dfb6d4ee147c816266bd3398ed236f3867c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 24189dfb6d4ee147c816266bd3398ed236f3867c
│           └── chunk-001.nq.gz
├── blob
│   ├── 028a57a19d49ed70c8f0dd2e202e28667500c742.nq.gz
│   ├── 074c016e958a6a6fd29c734d2f7782ed2ad462aa.nq.gz
│   ├── 0f510feaf9a6193b663998b71232e6a97a0a2afe.nq.gz
│   ├── 2365caa4a9984a3eba8bbef062b5322161372803.nq.gz
│   ├── 2b7b058329dfb7da5e10643462394667321c5be7.nq.gz
│   ├── 33003b3ee281490a2319c5e841b23ec6ba186dc0.nq.gz
│   ├── 38c31045959a1f86a93b7abe619c881359ecf3f7.nq.gz
│   ├── 3a35b9c2a6495c61c0e536c18fdb6478df13004a.nq.gz
│   ├── 43bf74ae5d441ce66ff0ae1702a9bc685202dbf8.nq.gz
│   ├── 44da9121a4dff316a8584c83824b36f52ee0da9f.nq.gz
│   ├── 5d3cc5b6784c403c2f8fd0d0482c1719f4a48c8a.nq.gz
│   ├── 694d7d58d440c236ea8ddcfece9eb605427f7be9.nq.gz
│   ├── 6ec6f6b0a54f4bc220728e33480d7a0f59425ae3.nq.gz
│   ├── 732f2e54f6ed6cf093f95ab52da009ae3d7af99a.nq.gz
│   ├── 7337ec994a461fef2123df891aea01aecff1834a.nq.gz
│   ├── 74ec657ae0fcef1334c0c19d27a6fa8857dae07a.nq.gz
│   ├── 8133ffe866fe54848e66ebfb6e54710243a1161e.nq.gz
│   ├── 8b5bdeafe022a83053aef2200f1df983990cfa32.nq.gz
│   ├── 98d9e64726070bfddfa79e497ed08e5901fbfb45.nq.gz
│   ├── 9a41aab8f5a359ef4c7855c7c2803a5e2b4de874.nq.gz
│   ├── a1c536607f7fcb9e29cd5ef23ab6695d739ca5da.nq.gz
│   ├── ab9bede26d3431b999c603f6d26a2ccd1a3df276.nq.gz
│   ├── b83c401d6e3b309cad06cdbf5db2a066f1cd45e1.nq.gz
│   ├── bf053346606c20f72030a3c8c4e00322d2277549.nq.gz
│   ├── c07d90ba02b303e44c11d95db1acb2818c468cb6.nq.gz
│   ├── c155b02bf2ffd43dc4d78b9c08a86ad3d0d21645.nq.gz
│   ├── c2555b8aa105543a3dfed75ec4096aa00a2b9d08.nq.gz
│   ├── c3f263973181e259a9ad8b19acea81f868b55d6a.nq.gz
│   ├── d0aaa1ef54febd9cccc7b559b79a172d4989bb54.nq.gz
│   ├── dec9f4930e75637361e18a2865419ac375b9e459.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f100fe191838be4cd234aaf4ba2788820fc2b938.nq.gz
│   ├── f2f8a78ad5a46cc025bb225e67e85cf41e00e20c.nq.gz
│   ├── fc06596e2b12f0abcff17aa45a05f6b5bff4467f.nq.gz
│   └── ffba7987e06945d1b58c4a43bf6f1837691713d5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 24189dfb6d4ee147c816266bd3398ed236f3867c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 43 files
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

[pytest-dev/pytest-factoryboy](https://github.com/pytest-dev/pytest-factoryboy)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
