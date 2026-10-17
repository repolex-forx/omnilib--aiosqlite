# Repolex Knowledge Graph of omnilib/aiosqlite

RDF knowledge graph data for [omnilib/aiosqlite](https://github.com/omnilib/aiosqlite), parsed by [repolex](https://repolex.ai).

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
rlex download omnilib/aiosqlite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9b127cecc7de843bf4f343b6da63b641866533fb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9b127cecc7de843bf4f343b6da63b641866533fb
│           └── chunk-001.nq.gz
├── blob
│   ├── 046f9b7803d6db3485599725ea79f985ecac37c4.nq.gz
│   ├── 06f32dc118cfc5cdec2ad9a10c4e7cf78614215e.nq.gz
│   ├── 0dc5b89c8071a5ab943d9646e9f6aba119d68b22.nq.gz
│   ├── 16150ec4c941f337dea494e11655d3d182c35ee1.nq.gz
│   ├── 1bf3d737f356acbe76535678a0c46384f90cfcfc.nq.gz
│   ├── 1c241b99f0e27ed9ef602c5f5d09fed36af3eb8c.nq.gz
│   ├── 389f6c5ac0039cd917c4516dfcddbf85bf0c7cbe.nq.gz
│   ├── 4adc274c6fb979986085191187b4491b744b4d9b.nq.gz
│   ├── 53d792b74dee1eabe8980fa52057847a9c0e12c3.nq.gz
│   ├── 56709fede6215dce2365f0b32db3c42c3542fc68.nq.gz
│   ├── 56d6af0d76bc419f419d68b65a836d76f3e9ae68.nq.gz
│   ├── 5afbaef534099b7d1dad8d79e4edd79e89e1b080.nq.gz
│   ├── 5cd13dba42d9ecb21deb602c01bbfeffbe83c07f.nq.gz
│   ├── 63656c1f909019083977b7135c0b2252c2d44200.nq.gz
│   ├── 64ad321dfff2eb592df2776b35a1cf9131f44f1c.nq.gz
│   ├── 69328745d08b60d92950612b89d3864c3d52afa9.nq.gz
│   ├── 6c37ff11e0f550a7241d23bfa9649efca814d25c.nq.gz
│   ├── 6e4ccb290b6842f06bcdaf0efd20d03d25ac21f8.nq.gz
│   ├── 89f3c22c951c2f6cdc84d6602cd03d4be33626f8.nq.gz
│   ├── 8b57f7c91ff4c5ca04951bb6b1c06e72bdef0013.nq.gz
│   ├── 8fc25e7684ad73d6b2e97c8af4d0ba3ffb51839f.nq.gz
│   ├── 953a14c75df0a434bf7fe79d596a0059eebe4941.nq.gz
│   ├── 99a70de62e49e41c4ea568ebc1a9a00f23534fc8.nq.gz
│   ├── a715624e023da78dd0b8fbd9a3a024f356cade41.nq.gz
│   ├── ab8f3f77e515b98323bb263a30b38c710eb33bfd.nq.gz
│   ├── bbb5ba0168e9e88b4f85237f52b09c9d63e19107.nq.gz
│   ├── c376be0599cec0d54fb6fa2a733bf205d6481e39.nq.gz
│   ├── c4491136e0c29b3e8f1f2b9b5ddbb76f045c7550.nq.gz
│   ├── c4c5bf94c1135d123d368ab6a1696156ee2a26fe.nq.gz
│   ├── ca0cb7edfee146425ff04085a562f73903794879.nq.gz
│   ├── cad75044c77b475eab9aff91810eb6d35cc63d13.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fc2b79bbc52460af305251d2985f50e9bcadf180.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9b127cecc7de843bf4f343b6da63b641866533fb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
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

[omnilib/aiosqlite](https://github.com/omnilib/aiosqlite)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
