# Repolex Knowledge Graph of sphinx-contrib/zopeext

RDF knowledge graph data for [sphinx-contrib/zopeext](https://github.com/sphinx-contrib/zopeext), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/zopeext
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 08c983e2df9646558d23b41c3bd01ce8e7c901ab
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 08c983e2df9646558d23b41c3bd01ce8e7c901ab
│           └── chunk-001.nq.gz
├── blob
│   ├── 0beea6d4d8345bd540d355c47a1ff9be244541e9.nq.gz
│   ├── 11d8a5f9a54bb1103c7ab6ec3aa272ae48e6029c.nq.gz
│   ├── 178144ef0d867886b3890d4ba88a541627ec4b7d.nq.gz
│   ├── 2629f9fcb7141a44a3ca0547b3b45eb721b0d0a6.nq.gz
│   ├── 2f93f9c8a2bf1f61d05100ffe8d3bc80d28748d9.nq.gz
│   ├── 4fbb64d6e67e41beaa53a5477e72f9a102437b7c.nq.gz
│   ├── 5127720920608ad9cf2130c8baebdca61c4f5451.nq.gz
│   ├── 54eda87f14349aac94564510b5e99c8f40c78f46.nq.gz
│   ├── 56b0858c7127847ef77d29883f9306ded1a3a6fa.nq.gz
│   ├── 58de3f683f0794acb5be3675e60032e8e92cbd63.nq.gz
│   ├── 5ff9a2af66ba65862cc41772fbfb815850aa4907.nq.gz
│   ├── 6041ebf14dcf31c3bf58bc41c9bb8d3781d6c3c3.nq.gz
│   ├── 6477e61dea437bcdb187a8904c31053cf1f66cfb.nq.gz
│   ├── 6b34400940db086580f3feb9780eda2a56769515.nq.gz
│   ├── 7c33a5ac8c78f8497ab850de6860323b633f8895.nq.gz
│   ├── 7c7bb0f938e04b91726be7903b85fdc178e47a0d.nq.gz
│   ├── 7ec624492eb17e289d128af4c139b6994448c38b.nq.gz
│   ├── 84dfcb894b4837f5be044a69110f6328620d69ca.nq.gz
│   ├── a00762e67d3744ed6f52203cb07e6db130321784.nq.gz
│   ├── a07e120c5658d99ca5ca677213e3f63982ac2be6.nq.gz
│   ├── abd65d488f5bfc4cf3832b90162c59c069efb80c.nq.gz
│   ├── b50c73e30a4d977a4d83f212c340f872eaad14ba.nq.gz
│   ├── b58c26a79d51bd6b37f94b3978c1bd91658e7bdd.nq.gz
│   ├── b83ff0a3ad42e3d550634bea7e89fd199aba3598.nq.gz
│   ├── bf2f9908101098cace6a891359f6fb1c8c3d0f7f.nq.gz
│   ├── c4542d4236c7ec7dace5e48deff52ae9f47f15ca.nq.gz
│   ├── c8ffcf33d20d570033eb85db4a369565da4ffb80.nq.gz
│   ├── cd1ee63b76bcb6f09b26b3e4facca9088b7569fa.nq.gz
│   ├── ce1ab2219a6cf403ff59fa0bbe88137bf6b03e79.nq.gz
│   ├── e0d18a4b1e8082675ee7c5dd17d85cd7c9abf2be.nq.gz
│   ├── e449e00926b228aa46231effc6954e363d7f6c37.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e9112560a551434e01d730682b1c5dd7faa5033b.nq.gz
│   ├── f122e38346377b9309b64a4a85782bc729c2fddf.nq.gz
│   ├── f45dc0c6bd68bb4fc30e09f01a135b6c061b6a24.nq.gz
│   ├── fa02d6cab333c7b7b8befdf40984752f71256618.nq.gz
│   └── fa0fec758ffdcec4b464a7263cba9bc94f489f3a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 08c983e2df9646558d23b41c3bd01ce8e7c901ab.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[sphinx-contrib/zopeext](https://github.com/sphinx-contrib/zopeext)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
