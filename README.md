# Repolex Knowledge Graph of jupyter/team-compass-template

RDF knowledge graph data for [jupyter/team-compass-template](https://github.com/jupyter/team-compass-template), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter/team-compass-template
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c12f15423ce3ffda5c68bed4dc614c02eb438ddf
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c12f15423ce3ffda5c68bed4dc614c02eb438ddf
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b606ec30294417d895b9d7f176f751119460a00.nq.gz
│   ├── 12ccd9427858abb36e3c08f8de7cc67ce6848b63.nq.gz
│   ├── 22cd887a458f47bdd60a2210d77384b6fe4cf2de.nq.gz
│   ├── 3a98f526969aec65f15b626dd8dc3fe00ee866cb.nq.gz
│   ├── 4ca97d3cb7559a8494be26d646be953ab60ec284.nq.gz
│   ├── 598b4e6475041fe11f12c99787e22d6be2f42548.nq.gz
│   ├── 6369dedffa186c53800075613882ef3e9d8890ef.nq.gz
│   ├── 693956812a13b23066f63cb7f1bc954d1e46e435.nq.gz
│   ├── 6fff6fea1e6322fac993f2b766d00d30e154b48a.nq.gz
│   ├── 7414a34cc680e9866efda983278033f0bbdbe400.nq.gz
│   ├── 7aaeae5eb0e9229ca935836abd262adbd8299cd6.nq.gz
│   ├── 8dcd05499c5ea45ce2317bbab135990598313237.nq.gz
│   ├── 950164b621c17720afa6912754a3a98d8cc1428b.nq.gz
│   ├── 9bd6dc65b8f10731be96d094484d8e54452db79f.nq.gz
│   ├── c0dc7aa890dfe2e6224e9fae64cea0306f21421e.nq.gz
│   ├── d6b98a51c238386d8f05b8d8f814783ed254529f.nq.gz
│   ├── e08b120d1e51a948a7e024b7e0094ec7e31d58b2.nq.gz
│   ├── e72ab8bbf2cfe3fcded217af25bf5992e48baff6.nq.gz
│   ├── fa25c2e371be82f38f61daf5fd2402b10fe53453.nq.gz
│   └── fc2799dd86d9fc2a2d1d01995967177c2d00cc73.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c12f15423ce3ffda5c68bed4dc614c02eb438ddf.nq.gz
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

[jupyter/team-compass-template](https://github.com/jupyter/team-compass-template)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
