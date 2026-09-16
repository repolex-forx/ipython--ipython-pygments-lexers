# Repolex Knowledge Graph of ipython/ipython-pygments-lexers

RDF knowledge graph data for [ipython/ipython-pygments-lexers](https://github.com/ipython/ipython-pygments-lexers), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download ipython/ipython-pygments-lexers
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 76f70093e2d354e6a2f4f42a7aed53018eff580c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 76f70093e2d354e6a2f4f42a7aed53018eff580c.nq.gz
│   └── repolex
│       └── 76f70093e2d354e6a2f4f42a7aed53018eff580c
│           └── chunk-001.nq.gz
├── blob
│   ├── 21c7b7e062c96e8da583de8b6a815c4bfca190ea.nq.gz
│   ├── 398ca1653aed60d77ad95d6917bc6902c561427f.nq.gz
│   ├── 5818e3fde1d51f119d2e81ef24a45e7b8a77680f.nq.gz
│   ├── 84079b0e9f98cd6e4f677ac929c1d445cb192acc.nq.gz
│   ├── b1fa2b924611957cf2b93aab8d574afb29903b7b.nq.gz
│   ├── c655e233654b8ddf8d9a18638451a1ad6937e1d8.nq.gz
│   ├── dd9535964c7e0e73470ca74570d012d315afb52f.nq.gz
│   └── dfd5ad080930e1cd0a4eeae7c11997b2a8a04c7c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 76f70093e2d354e6a2f4f42a7aed53018eff580c.nq.gz
├── filetree
│   └── 76f70093e2d354e6a2f4f42a7aed53018eff580c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 18 files
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

## Source repository

[ipython/ipython-pygments-lexers](https://github.com/ipython/ipython-pygments-lexers)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
