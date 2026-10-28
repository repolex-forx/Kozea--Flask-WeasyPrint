# Repolex Knowledge Graph of Kozea/Flask-WeasyPrint

RDF knowledge graph data for [Kozea/Flask-WeasyPrint](https://github.com/Kozea/Flask-WeasyPrint), parsed by [repolex](https://repolex.ai).

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
rlex download Kozea/Flask-WeasyPrint
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9c7b3f40f13dc8878aaf367e86b24f11c2d37fd2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9c7b3f40f13dc8878aaf367e86b24f11c2d37fd2
│           └── chunk-001.nq.gz
├── blob
│   ├── 147ddba26b2d990189439ddeda26e9af49fc7412.nq.gz
│   ├── 1e3a698db54b192fa89d52edb190d397de05c2b4.nq.gz
│   ├── 1ff9b86120241b29da4a3443ace196cd1db87720.nq.gz
│   ├── 3efca7f9492f9dde762c0657023d4392a577bb78.nq.gz
│   ├── 507bf242221d66043daa5c8eee27d3f5db7d1a11.nq.gz
│   ├── 6fc61572ed881a249a808756a652f9d7e58314e3.nq.gz
│   ├── 733235625800dc3bab0350feba12caf4fb3b1f79.nq.gz
│   ├── 89859f2f332a1fd5f4cba18c5bf2deedf5fabaed.nq.gz
│   ├── 9a9357c6c0d1c374544cf6d78ea8ecb566066e16.nq.gz
│   ├── a1524d145124f4949bbb72043ac4deac352025b4.nq.gz
│   ├── a83c330e88db0f6a8584c0da88652de66adf6653.nq.gz
│   ├── ae1866093321967d6fa3a013d0080e0d5c1c3ac2.nq.gz
│   ├── b560280f4aab5751c071b59d41adb14ca98ed857.nq.gz
│   ├── b9c8490306a0a16a88ac67c24b16ba996cb66dbc.nq.gz
│   ├── c8f14da4b9a17df6954cf4b25831f2cbbd5e7637.nq.gz
│   ├── cfdb58850b0b439b1f88df30416d75b52541b432.nq.gz
│   ├── d1106d665e35b485dbb25b977e98618fa947e36d.nq.gz
│   ├── d4d0fe58f017eca938face9d3335ee07914ffb45.nq.gz
│   ├── dcc20cdcae59903b0617ef125da23bfcbe7a883b.nq.gz
│   └── fa598978fa19e892be771209bed03293f34b4d74.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9c7b3f40f13dc8878aaf367e86b24f11c2d37fd2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[Kozea/Flask-WeasyPrint](https://github.com/Kozea/Flask-WeasyPrint)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
